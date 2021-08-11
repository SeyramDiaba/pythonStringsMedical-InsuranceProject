medical_data = \
"""Marina Allison   ,27   ,   31.1 , 
#7010.0   ;Markus Valdez   ,   30, 
22.4,   #4050.0 ;Connie Ballard ,43 
,   25.3 , #12060.0 ;Darnell Weber   
,   35   , 20.6   , #7500.0;
Sylvie Charles   ,22, 22.1 
,#3022.0   ;   Vinay Padilla,24,   
26.9 ,#4620.0 ;Meredith Santiago, 51   , 
29.3 ,#16330.0;   Andre Mccarty, 
19,22.7 , #2900.0 ; 
Lorena Hodson ,65, 33.1 , #19370.0; 
Isaac Vu ,34, 24.8,   #7045.0"""

# Add your code here
print(medical_data)
print("--------------------------------")
#replacing # with $
updated_medical_data=medical_data.replace("#","$")
print(updated_medical_data)
#number of medical records
num_records=0
for num in updated_medical_data:
  if num == "$":
    num_records += 1
print("------------------------------")
print(num_records)
print("------------------------------")
#splitting string into a list
medical_data_split= updated_medical_data.split(";")
print(medical_data_split)
print("------------------------------")
#split each medical record into it's own list
medical_records=[]
for medical in medical_data_split:
  medical_records.append(medical.split(","))
print(medical_records)

#stripping and append record_clean to medical_records_clean
medical_records_clean=[]
for records in medical_records:
  record_clean=[]
  for item in records:
    record_clean.append(item.strip())
  medical_records_clean.append(record_clean)

print("------------------------------")
print(medical_records_clean)
print("------------------------------")

for record in medical_records_clean:
  print(record[0].upper())
print("-------------------------------")
#empty lists
names = []
ages = []
bmis = []
insurance_costs = []

for allocate in medical_records_clean:
  names.append(allocate[0])
  ages.append(allocate[1])
  bmis.append(allocate[2])
  insurance_costs.append(allocate[3])

print(names)
print(ages)
print(bmis)
print(insurance_costs)
print("---------------------------------")

#Calculating the average bmi
total_bmi = 0
for avg in bmis:
  total_bmi += float(avg)
#average***
average_bmi= total_bmi/len(bmis)
print("Average BMI: "+ str(average_bmi))
print("---------------------------------")
#EXTRA
#Calculate avg insurance cost

total_insurance = 0
for insure in insurance_costs:
  total_insurance += float(insure.strip("$"))

#average insurance cost
average_insurance_cost = total_insurance/len(insurance_costs)

#loop to print statements
for i in range(0,len(insurance_costs)):
  print(names[i] + " is " + str(ages[i]) + " years old with a BMI of " +str(bmis[i])+ " and an insurance cost of " + str(insurance_costs[i]) + ".")

print("--------------------------------")
#completed




  