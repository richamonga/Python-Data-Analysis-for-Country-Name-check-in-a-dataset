# Python-Data-Analysis-for-Country-Name-check-in-a-dataset
Recently I started my journey towards extensively using Python for Data Analysis and there were so many instances where I encountered data sets which contained country names.The problem was how do I validate if country names coming in millions of rows in my data set were correct or not?  Have you ever came across such issue? If yes,then this post shall be helpful for you.I have written a function in Python which can be used to find out incorrect country names coming in a data set.

I have demoed this by implementing it on a Kaggle data set which has incorrect county names in its country data.

Data Source : timesData.csv from ‘World University Rankings’ data set on Kaggle

This data set has incorrect/misspelled entries for country name like : Unisted States of America,Unted Kingdom. 

This function uses ‘pycountry’ library of Python which contains ISO country names.It provides two-alphabet country name,three-alphabet country name,name,common name,official name and numeric country code.

This function compares country name coming in the input list with each of the following provided by pycountry.countries:

alpha_2 : Two character country code

alpha_3 : Three character country code

name: Country name

common name : Common name for the country

official name : Official name for the country

Also,comparison is being done by converting each of the above attribute content into upper case since we have input country name list also in upper case.

Another thing to be noted here is that,I have created a list called ‘tobe_deleted’ in the function definition.This list contains of those countries for which we have different version of name in pycountry and therefore we do not want these countries to appear as invalid country names when our function is called.

Example:

1.MACAU is also spelled as MACAO,therefore both the sames are valid.However,pycountry.countries has only one entry with spelling as MACAO.country_name_check() can handle both MACAO and MACAU.

2. Similarly, pycountry.countries has entry for IRELAND with name=’Ireland’.However,it is also sometimes referred as ‘Republic of Ireland’.country_name_check() can handle both ‘Ireland’ and ‘Republic of Ireland’ in input data set.

I hope this function helps all the people who might have faced issues with handling invalid country names in data sets at any point during data analysis.
