# CompanyManagement Playground
 
 - CompanyManagementApp.playgorund, şirket ismi, kuruluş yılı, bütçe ve varsa çalışan parametreleriyle şirket oluşturduğumuz bir playground dosyasıdır. Kurduğumuz şirkete ister kuruluşta ister daha sonrasında çalışan eklenebilir veya çıkarılabilir, bütçeye gelir & gider eklenebilir ve bütçeden maaşlar ödenebilir.

- Şirket kuruluşunda çalışan eklemek optional'dır (default değeri nil). Eğer şirket, çalışanlar ile oluşturulacaksa Company class'ı initilize edilmeden önce Employee class'ından çalışanları barındıran bir array oluşturulmalıdır. Bu array Company class'ının initializer'ında parametre olarak kullanılacaktır.

- Eğer şirket çalışansız oluşturulacaksa Company class'ı initializer'ında employees parametresi kullanılmamalıdır.
- Çalışanlar sonradan hireEmployee fonksiyonu ile eklenebilir. Çalışan eklerken id'nin farklı olması gerekmektedir. Eğer aynı id'li çalışan eklenmeye çalışılırsa uyarı alınacaktır ve çalışan oluşturulamayacaktır.

- Çalışan çıkarılmak istenirse fireEmployee fonksiyonuna çalışan ismi(case insensitive) ve çalışan id'si verilmelidir.

- paySalary fonksiyonu ile çalışan maaşları ödenir. Completion'ında Employee array döner. Bu array'den maaşlar ödendikten sonra kime ne kadar maaş ödenmiş gibi bilgiler öğrenilebilir.
- addIncome fonksiyonu ile bütçeye gelir, addExpense ile bütçeye gider eklenebilir.

### SUCCESS MESSAGES:

- Şirket oluştuğunda: "\(name) Company is created in \(year) with \(employees?.count ?? 0) employee(s) and the budget of \(budget)₺"
- Çalışan çıkarıldığında: "\(employee.name) with id: \(employee.id) is fired."
- Çalışan eklendiğinde: "Employee \(name) is hired."
- Gelir eklendiğinde: "Income is added. Previos budget: \(previousBudget)₺, new budget: \(budget)₺"
- Gider eklendiğinde: "Expense is added. Previos budget: \(previousBudget)₺, new budget: \(budget)₺"
- Maaşlar ödendiğinde: "\(totalSalary)₺ employee salaries are paid. Remaining budget: \(budget)₺."

### FAILURE MESSAGES:

- Çalışan yokken çalışan çıkarmak istendiğinde: "There is no employee to fire."
- Çalışan çıkarılırken verilen parametrelere uyan çalışan yoksa: "There is no \(name) with id: \(id) employee to fire."
- Yeni çalışan eklenirken mevcut çalışana ait bir id denendiğinde: "There is already an employee with id: \(employeeId). Please try another id."
- Bütçede yeterli tutar yokken expense girilmek istendiğinde: "There is not enough money to pay expense. Please add income to budget case."
- Çalışan maaşları ödenmek istendiğinde yeterli bütçe yoksa: "There is not enough money to pay salaries. Please add income to budget case."
- Çalışan yokken çalışan maaşı ödenmek istendiğinde: "There is no employee to pay salary."
