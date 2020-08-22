# corona_virus_tracker_Application

#pip install covid

Code is as follows:

from covid import Covid
import matplotlib.pyplot as pyplot

country= input("Enter your country name : ")
covid=Covid()
data=covid.get_status_by_country_name(country)

cadr={
    key:data[key]
    for key in data.keys() & {"confirmed","active","deaths","recovered"}

}
n=list(cadr.keys())
v=list(cadr.values())
print(cadr)

pyplot.title(country)
pyplot.bar(range(len(cadr)),v,tick_label=n) #using bar plot
pyplot.show()
