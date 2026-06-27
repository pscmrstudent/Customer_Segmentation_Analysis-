rfm['R'] = pd.qcut(rfm['Recency'],5,labels=[5,4,3,2,1])

rfm['F'] = pd.qcut(rfm['Frequency'].rank(method='first'),5,
                   labels=[1,2,3,4,5])

rfm['M'] = pd.qcut(rfm['Monetary'],5,
                   labels=[1,2,3,4,5])

rfm['RFM_Score'] = (
    rfm['R'].astype(str)+
    rfm['F'].astype(str)+
    rfm['M'].astype(str)
)
