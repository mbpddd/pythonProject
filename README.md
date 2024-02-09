#3. Переписать класс Employee, в котором будут реализованы следующие методы:
#a. Возможность создавать Employee с помощью init ( данные вводятся пользоваталем)
#b*. Альтернативный конструктор (способ создания Employee), который будет принимать строку
#в формате 'Oleg-Huesosov-1920-ваши-остальные-поля' и создавать объекты формартируя эту строку(ПАРСИТЬ!!!!!!!!!!)(подсказки: format(), split(),return)

class Employee:
    instances = []
    def __init__ (self,name,age,salary):
        self.name = name
        self.age = age
        self.salary = salary
        Employee.instances.append(self)
    def  convert (self,data_str):
        name,age,salary=data_str.split('-')
        return self.__class__(name,age,salary)
    def data_output(self):
        print('\n''Name is: ',self.name)
        print('Age is: ',self.age)
        print('Salary = ',self.salary)
employee_instance = Employee(' ', ' ', None)
aas ='Alezhka-20-20000.2'
bs ='Pisunchik-19-2000,32'
cs ='Govnoed-12-42,5'
a = employee_instance.convert(aas)
b = employee_instance.convert(bs)
c = employee_instance.convert(cs)
a.data_output()
b.data_output()
c.data_output()
