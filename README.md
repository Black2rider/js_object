1. Задача. Подсчёт свойств
Задание
Напиши функцию countProps(object), которая считает и возвращает количество собственных свойств объекта в параметре object. Используй переменную propCount для хранения количества свойств объекта.


    		function countProps(object) {
		  let propCount = 0;
		  // Change code below this line
		 for (const key in object) {
		    if (object.hasOwnProperty(key)) {
		      propCount += 1;
		    }
		  }
		  // Change code above this line
		  return propCount;
		}
		
		
		function countProps(object) {
		  // Change code below this line
		  let propCount = 0;
		  const keys = Object.keys(object);
		  for (const key of keys) {
		      propCount = keys.length;
		  }
		  return propCount;
		  // Change code above this line
		}



2. Перебери объект apartment используя метод Object.keys() и цикл for...of. Запиши в переменную keys массив ключей собственных свойств объекта apartment, и добавь в массив values все значения его свойств.

		const apartment = {
		  descr: 'Просторная квартира в центре',
		  rating: 4,
		  price: 2153,
		};
		const values = [];
		// Пиши код ниже этой строки
		const keys = Object.keys(apartment);
		for (const key of keys) {
		  values.push(apartment[key]); 
		}



3. Напиши функцию countTotalSalary(salaries) которая принимает объект зарплат, где имя свойства это имя сотрудника, а значение свойства это зарплата. Функция должна рассчитать общую сумму зарплат сотрудников и вернуть её. Используй переменную totalSalary для хранения общей суммы зарплаты.

		function countTotalSalary(salaries) {
		  let totalSalary = 0;
		  // Change code below this line
		  const keys = Object.values(salaries);
		  for (const key of keys) {
		    totalSalary += key; 
		  }
		  // Change code above this line
		  return totalSalary;
		}



4. Напиши функцию getProductPrice(productName) которая принимает один параметр productName - название продукта. Функция ищет объект продукта с таким именем (свойство name) в массиве products и возвращает его цену (свойство price). Если продукт с таким названием не найден, функция должна возвращать null.

		const products = [
		  { name: 'Радар', price: 1300, quantity: 4 },
		  { name: 'Сканер', price: 2700, quantity: 3 },
		  { name: 'Дроид', price: 400, quantity: 7 },
		  { name: 'Захват', price: 1200, quantity: 9 },
		];

		function getProductPrice(productName) {
		  // Пиши код ниже этой строки
		  let value = null;
		  for (product of products) {
		     if (productName === product.name) {
			value = product.price;
		     }
		  }
		    return value;

		  // Пиши код выше этой строки
		}
		console.log(getProductPrice('Двигатель'));



5. Напиши функцию getAllPropValues(propName) которая принимает один параметр propName - имя (ключ) свойства. Функция должна вернуть массив всех значений свойства с таким именем из каждого объекта в массиве products. Если в объектах нет свойства с таким именем, функция должна вернуть пустой массив.

		const products = [
		  { name: 'Радар', price: 1300, quantity: 4 },
		  { name: 'Сканер', price: 2700, quantity: 3 },
		  { name: 'Дроид', price: 400, quantity: 7 },
		  { name: 'Захват', price: 1200, quantity: 9 },
		];

		function getAllPropValues(propName) {
		  // Пиши код ниже этой строки
		 const arrow = [];
		   for (const product of products) {
		     if (product[propName]) {
			arrow.push(product[propName]);
		     }
		   }
		  return arrow;
		  // Пиши код выше этой строки
		}



6. Задача. Общая стоимость товара
Задание
Напиши функцию calculateTotalPrice(productName) которая принимает один параметр productName - название товара. Функция должна вернуть общую стоимость (цена * количество) товара с таким именем из массива products.

		const products = [
		  { name: 'Радар', price: 1300, quantity: 4 },
		  { name: 'Сканер', price: 2700, quantity: 3 },
		  { name: 'Дроид', price: 400, quantity: 7 },
		  { name: 'Захват', price: 1200, quantity: 9 },
		];

		function calculateTotalPrice(productName) {
		  // Пиши код ниже этой строки
		 let total = 0;
		  for (const product of products) {
		    if (productName === product.name) {
		      total = product.price * product.quantity;
		    }
		  }
		  return total;

		  // Пиши код выше этой строки
		}



7. Задача. Карточки задач
Задание
Напиши функцию makeTask(data) которая принимает один параметр data - объект со следующими свойствами.

text - текст задачи.
category - категория задачи.
priority - приоритет задачи.
Функция должна составить и вернуть новый объект задачи, не изменяя напрямую параметр data. В новом объекте должно быть свойство completed, значение которого хранится в одноимённой локальной переменной.

В параметре data гарантированно будет только свойство text, а остальные два, category и priority, могут отсутствовать. Тогда, в новом объекте задачи, в свойствах category и priority должны быть значения по умолчанию, хранящиеся в одноимённых локальных переменных.

		function makeTask(data) {
		  const completed = false;
		  const category = 'Общее';
		  const priority = 'Обычный';
		  // Пиши код ниже этой строки
		  const copyData = {completed, category, priority, ...data};
		  return copyData;
		  // Пиши код выше этой строки
		}



8. Задача. Массив совпадений
Задание
Функция findMatches() принимает произвольное количество аргументов. Первым аргументом всегда будет массив чисел, а остальные аргументы будут просто числами.

Дополни код функции так, чтобы она возвращала новый массив matches, в котором будут только те аргументы, начиная со второго, которые есть в массиве первого аргумента.

Например, findMatches([1, 2, 3, 4, 5], 1, 8, 2, 7) должна вернуть массив [1, 2], потому что только они есть в массиве первого аргумента.

		// Пиши код ниже этой строки
		function findMatches(...args) {
		  const matches = []; // Не изменяй эту строку
		  for (const arg of args) {
		    const firstElement = args[0];
		    console.log(firstElement);
		    if (firstElement.includes(arg)) {
		       matches.push(arg);
		    }
		  }
		  // Пиши код выше этой строки
		  return matches;
		}



9. Задание
Дополни метод updateBook(oldName, newName) так, чтобы он изменял название книги с oldName на newName в свойстве books. Используй indexOf() для того, чтобы найти нужный элемент массива, и splice() для того чтобы заменить этот элемент.

		const bookShelf = {
		  books: ['Последнее королевство', 'Мгла', 'Страж снов'],
		  updateBook(oldName, newName) {
		    // Пиши код ниже этой строки
			const ind = this.books.indexOf(oldName);
			this.books.splice(ind, 1, newName);
		    return this.books;
		    // Пиши код выше этой строки
		  },
		};



Задача. Расширяем инвентарь
Задание
Заказчица хочет чтобы каждое зелье было представлено не только именем, но и ценой, а в будущем может быть и другими характеристиками. Поэтому теперь в свойстве potions будет храниться массив объектов со следующими свойствами.

{
  name: "Dragon breath",
  price: 700
}
Выполни рефакторинг методов объекта atTheOldToad так, чтобы они работали не с массивом строк, а с массивом объектов.

getPotions() - метод для получения всех зелий. Возвращает значение свойства potions.
addPotion(newPotion) - добавляет зелье newPotion (уже объект) в массив в свойстве potions, но только если такого зелья еще нет в инвентаре. В противном случае возвращается строка.
removePotion(potionName) - удаляет объект зелья с именем potionName из массива в свойстве potions.
updatePotionName(oldName, newName) - обновляет свойство name объекта-зелья с названием oldName на newName в массиве potions.

		const atTheOldToad = {
		  potions: [
		    { name: "Speed potion", price: 460 },
		    { name: "Dragon breath", price: 780 },
		    { name: "Stone skin", price: 520 },
		  ],
		  // Change code below this line
		  getPotions() {
			    return this.potions;
			  },

			  addPotion(newPotion) {
			    for (const el of this.potions) {
			   if (el.name === newPotion.name) {
			      return `Error! Potion ${newPotion.name} is already in your inventory!`;
			      }
			}
			    this.potions.push(newPotion);
			  },

			  removePotion(potionName) {
			    const {potions} = this;

			    for (let i = 0; i < potions.length; i += 1) {
			      if (potionName === potions[i].name) {
			      potions.splice(i, 1);
			      }

			    }
			return `Potion ${potionName} is not in inventory!`;
			  },
			  updatePotionName(oldName, newName) {

			    for(const potion of this.potions) {
			       if (potion['name'] === oldName) {
				 potion['name'] = newName;
			       }
			    }
			  }
		  // Change code above this line
		};
		console.log(atTheOldToad.addPotion({ name: "Dragon breath", price: 700 }));
