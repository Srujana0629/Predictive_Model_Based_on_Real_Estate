# Predictive Model Based on Real_Estate
## Problem Statement 

The  primary  objective  of  this  project  is  to  develop  a  predictive  regression  model  that  can accurately forecast real estate sales prices based on a comprehensive set of predictors. By  leveraging  advanced  analytics  techniques  and  machine  learning  algorithms,  the regression  model  aims  to  provide  actionable  insights  to  stakeholders,  enabling  them  to make informed decisions and optimize their real estate transactions. 

## Dataset Overview 

### Link : 
https://www.kaggle.com/datasets/subhiarjaria09/real-estate-property-transactions-dataset 
The  dataset  is  collected  from  Kaggle  holding  10,000  instances  with  12  variables.  The data  type  contains  integer,  object  &  float.  The  explanations  of  the  variables  are  stated below- 

## Features: 
●  Date:  Date of the property transaction. 
●  Year:  Year of the property transaction. 
●  Locality:  Locality or area where the property is situated. 
●  Estimated Value:  Estimated monetary value of the property. 
●  Sale Price(Target) :  Actual sale price of the property. 
●  Property Type:  Type of property (e.g., Single Family,  Condo). 
●  Residential:  Indicates whether the property is designated  for residential use. 
●  Number of Rooms:  Total number of rooms in the property. 
●  Number of Bathrooms:  Total number of bathrooms in  the property. 
●  Carpet Area:  Area covered by carpet within the property  (in square feet). 
●  Property Tax Rate:  Tax rate applied to the property's assessed value. 
●  Facing  Direction:  Direction  the  main  entrance  or  facade  of  the  property  is 
oriented towards (e.g., North, South, East).

## Data Preprocessing 

Dropped  Column(Data):  As  the  dataset  has  12  years  of  instances  and  we  will  be analyzing  our  data  on  a  yearly  basis,  we  dropped  the  column  “date”  as  it  is  not  very useful for our analysis.Checked  for  Duplicate  Values  :  Initially  we  observed  to  check  if  there  are  any duplicate columns in the dataset. Therefore,We didn’t find any duplicates. Checked  for  the  Unique  Values  :  These unique  value  counts  provide  insights  into  the diversity  and  variability  present  in  each  column  of  the  dataset,  which  is  essential  for understanding  dataset's  characteristics  and  potential  analysis approaches.  We  checked the  value  count  of  each  unique  variable  in  the  types  of  property  column  and  found  1788 “?”  Values,  which  have  been  dealt  and  replaced  with  another  predefined  value  NaN  by value mapping imputation (using lambda function). Iterative  Imputation  to  replace  Null  Values  in  Numerical  Columns:  Checking  for missing  value  returns  a  Boolean  dataframe  indicating  whether  each  element  is  missing or  not.  Then  we  summed  up  the  missing  values  for  each  column,  and  the  result  is divided  by  the  total  number  of  rows  to  calculate  the  percentage  of  missing  values  in each column.  Later,  we  filtered  out  the  columns  with  missing  values  greater  than  0  that showed  these  4  columns  -  'Locality',  'Estimated  Value',  'Property',  and  'carpet_area’. Another  check  was performed  to  see  if  there  are  columns  that  have  missing  values greater  than  50  %.  Lastly  we  used  an  iterative  imputer  to  impute  the  missing  values  with mean  and fitted in the numerical column to transform. Standardization  :  To  bring  features  into  similar  scales,  we  have  standardized  the numerical  columns  to  bring  mean  of  0  and  standard  deviation  of  1  by  using  standard scalar. Random Sampling  Method  :  Likewise  numerical  columns,  we  selected  the  categorical values  and  checked  for  the  missing  value  percentages,  that  checks  the  missing  values above  0.  Then  we  imputed  the  missing  values  with  random  sampling  method  which randomly samples based on the category of the dataset. Removed  Duplicate  Rows  :  After  Concatenating  both  numerical  and  categorical values we found a duplicate row #9878 and we dropped this row. One  Hot  Encoding  :  Lastly,  we  splitted  numerical  and  categorical  columns  once  again and  used  one  hot  encoding  that  created dum variables  for  each  categoricals,  and dropped the first level to avoid multicollinearity. This is how the dataset is preprocessed and made ready for further analysis.

##   Folium Map for Average Price by Locality

The  Folium  map  displays  the  average  sales  prices  of  properties  across  seven  cities  in Connecticut:  Bridgeport,  Waterbury,  Fairfield,  West  Hartford,  Greenwich,  Norwalk,  and Stamford.  Each  city  is  marked  with  a  location  pin,  and  when  clicked,  the  pin  reveals  the average  sales  price  for  that  specific  city.  This  Map  provides  a  quick  overview  of property  prices  in  different  areas,  aiding  users  in  understanding  the  varying  real  estate market dynamics across the selected cities.

## Dashboard 

In  today's  dynamic  real  estate  market,  understanding  housing  sale  prices  is  essential  for buyers,  sellers,  and  investors  alike.  Our  interactive  dashboard  offers  a  comprehensive analysis  of  housing sale  prices,  providing  valuable  insights  to  guide  your decision-making  process.  Through  this  dashboard,  users  can  explore  various  aspects  of the  housing  market,  including  trends  over  time, geographic  distribution,  and  factors influencing  pricing  fluctuations.  With  user-friendly  visualizations  and  intuitive  controls, navigating through the data has never been easier. Whether  you're  a  prospective  homebuyer  looking  for  the  perfect  property,  a  seller seeking  to  understand  market  trends,  or  an  investor  evaluating  potential  opportunities, this dashboard empowers with the knowledge needed to make informed decisions. 

### Link : 
https://public.tableau.com/app/profile/srujana.guggilla/viz/RealEstatePropertyTransact 
ionDashboard/SALEPRICEPREDICTIONS

## Modeling Building : 
We  have  outliers  in  our  data,  prompting  the  utilization  of  models  which  are  immune  to outliers.  So,  we  decided  to  go  with  the  following  models  for  the  regression  to  predict  our sale price. 
1.  Ada Boosting 
2.  XG Boost 
3.  Random Forest 
4.  Ridge and Lasso



