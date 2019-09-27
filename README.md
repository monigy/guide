# guide
# This programm can calculate fuel consumption, travel time, refuels and refuels_time

program = "Путеводитель"

stars = 60
tabs = 5

dist = 0
speed = 0
time = 0
total_time = 0
drive_hours = 0
drive_mins = 0
total_hours = 0
total_min = 0

tank = 0
consum = 0 
dist = 0
refuels = 0 
refuel_time = 20
fuel = 0 
price = 0

breaks = 0
break_time = 0

print("\t" * tabs, program)
print("*" * stars)

dist = int(input("Введите расстояние, км: "))
speed = int(input("Планируемая средняя скорость, км / ч: "))
consum = float(input("Введите средний расход л./100 км : "))
tank = float(input("Объем бака,л : "))
price = float(input("Стоимость 1л топлива, р.: "))
breaks = float(input("Количество плановых остановок (без дозаправок): "))
break_time = float(input("Время каждой плановой остановки, минут : "))

time = dist * 60 / speed
fuel = consum * dist / 100

refuels = fuel // tank
total_time = time + refuels + refuel_time + breaks + break_time

drive_hours = time // 60
drive_mins = time - drive_hours * 60

total_hours = total_time // 60
total_mins = time - total_hours * 60

print ("*" * stars)
print ("\t" * tabs, "Результаты")

print ("Время за рулем : ", int(drive_hours), " ч.", int(drive_mins), " м.")
print ("Общее время в пути : ", int(total_hours), " ч.", int (total_mins), " м.")
print ("Количество дозаправок" , refuels)
print ("Потрачено времени на дозаправку: ", refuels * refuel_time, " м.")
print ("Израсходавано топлива, л. : ", fuel)
print ("Стоимость топлива, р : ", fuel * price)
