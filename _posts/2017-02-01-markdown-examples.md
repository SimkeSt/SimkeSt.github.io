---
title:  "How to build basic recommender system for movies"
layout: post
---

## Data

For this school exercise we used Movielens dataset for movies. 

```python 
import pandas as pd
import math
import scipy
from scipy import sparse
import os
import numpy as np
import csv
import itertools



class SlopeOnePredictor():
    def __init__(self,user):
        self.user=user
    
    def fit(self):
        ratings = pd.read_csv('PROCESSEDRATINGDATA1.csv')  
        baba = ratings.pivot_table(index=['userID'],columns=['movieID'],values='rating')
        baba.fillna(0, inplace=True)
        return(self.sloppy_one(baba))
    
    def obradapodataka(self,ff,one,two):
        kek=ff[ff[one]!=0]
        lul=kek[kek[two]!=0]
        dazdingo=len(lul)
        qq=((lul[one].sum()-lul[two].sum())/dazdingo)
        return(qq,dazdingo)
    
    def sloppy_one(self,scp):

        dev = pd.DataFrame(index=scp.columns,columns=scp.columns)
        cardinality= pd.DataFrame(index=scp.columns,columns=scp.columns)
        for (columnName, columnData) in scp.iteritems(): 
            for (columnName1, columnData1) in scp.iteritems(): 
                if(columnName1!=columnName):
                    ff=scp[columnName1]
                    fq=scp[columnName]
                    df = pd.concat([ff, fq], axis=1)
                    t1,t2=self.obradapodataka(df,columnName,columnName1)
                    dev[columnName1][columnName]=t1
                    cardinality[columnName1][columnName]=t2
        
        qq=self.nadjusera(scp,dev,cardinality)
        return(qq)

                              
    def nadjusera(self,scp,dev,car):
        userid=self.user
        dd=scp.transpose()
        dd2=scp.transpose()
        nein= pd.DataFrame()
        nein2 = scp.transpose()
        dd[userid] = dd[userid].replace([0],np.nan)
        for (columnName, columnData) in scp.iteritems(): 
            ff=(dd[userid]+dev[columnName])*car[columnName]
            nein['rat']=ff
            nein['card']=car[columnName]
            nein.fillna(0,inplace=True)
            nein=nein[nein['rat']!= 0]
            ses=nein['card'].sum()
            ses2=nein['rat'].sum()
            nein2[userid][columnName]=(ses2/ses)
        kk=nein2[userid].sort_values(ascending=False)
        k1=pd.DataFrame(columns=[userid])
        k1[userid]=kk
        k1[k1>5]=5
        k1.columns = ['Score']
        return(k1)```