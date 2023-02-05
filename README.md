ЗАДАНИЯ НА СООБРАЗИТЕЛЬНОСТЬ
1 задание. Мой ответ – 70 человек. Из 90 человек получилось 110 утверждений. Человек, который врет – дает сразу два положительных утверждения. Это значит, что 110 – (110 – 90)*2 = 70  
2 задание. Мой ответ – возможно. Из 11 цифр у нас 5 нечетных и 4 четных. Если представить это в виде матрицы, то диагональ у них будет одинаковыми цифрами при умножении, а значит ее можно отбросить. Нужно всего лишь подобрать остальные цифры в каждом столбце и каждой строке, где одна четная, а вторая нечетная, которые дают одинаковое произведение. Вот пример такой матрицы:
7 3 10
5 11 8
6 4 9 
3 задание. Я не придумал ничего лучше, чем скидывать материал через каждые два метра. Это единственный способ узнать абсолютно точную высоту, имея всего лишь 2 попытки. Это значит, что максимум потребуется 2500 бросков, минимум – 1.
4 задание. Мой ответ – 60 пирожков. Это решается обычным уравнением, где х – всего пирожков, (х/3 + 2) – пирожков, которые купил первый студент, (х/4 + 3) – второй студент, (х/5 + 8) – третий студент. Получаем уравнение отсюда
х/3 + 2 + х/4 + 3 + х/5 + 8 = х
х/3 + х/4 + х/5 + 13 = х
20x + 15x + 12x + 780 = 60x
-13x = -780
х = 60 
 
ЗАДАЧИ ПО ПРОГРАММИРОВАНИЮ
JavaScript
1 задание. 
const printArray = (array) => {
  return array.join(", ") + ".";
};

2 задание.
const roundFloat = (digit) => {
  const whole = Math.round(digit);

  let lastdigit = digit % 10;

  if (lastdigit < 2.5) return parseInt(whole.toString().slice(0, -1) + 0);
  else if (lastdigit >= 2.5 && lastdigit < 7.5)
    return parseInt(whole.toString().slice(0, -1) + 5);
  else return parseInt(whole.toString().slice(0, -1)) * 10 + 10;
};


3 задание. 
const computerOutput = (digit) => {
  const computer = "компьютер";
  if (digit % 10 === 1) return digit + " " + computer;
  else if (digit % 10 >= 2 && digit % 10 <= 4)
    return digit + " " + computer + "a";
  else return digit + " " + computer + "ов";
};

4 задание. 
const primeTest = (digit) => {
  let count = 0;

  for (let i = 1; i < digit; i++) {
    if (digit % i === 0) count++;
  }

  if (count < 2) return true;
  else return false;
};

5 задание.
const arrayComparison = (arr1, arr2) => {
  let newSortedArr1 = [];
  let newSortedArr2 = [];
  let totalArray = [];

  arr1.sort((a, b) => a - b);
  arr2.sort((a, b) => a - b);

  for (let i = 0; i < arr1.length - 1; i++) {
    if (arr1[i] === arr1[i + 1]) newSortedArr1.push(arr1[i]);
  }
  
  for (let i = 0; i < arr2.length - 1; i++) {
    if (arr2[i] === arr2[i + 1]) newSortedArr2.push(arr2[i]);
  }

  for (let i = 0; i < newSortedArr1.length; i++) {
    for (let j = 0; j < newSortedArr2.length; j++) {
      if (newSortedArr1[i] === newSortedArr2[j]) {
        totalArray.push(newSortedArr1[i]);
      }
    }
  }
  return new Set(totalArray);
};

6 задание.
<input type="text" name="" id="value" /> <br /><br />
<input
  type="button"
  onclick="printMultiplicationTable()"
  value="Построить таблицу умножения"
/><br />
<div id="table"></div>

const printMultiplicationTable = () => {
  let addTable = document.getElementById("table");
  const val = document.getElementById("value").value;

  let table = "<table style='text-align: right;'><tr>";
  for (let i = 1; i <= val; i++) {
    for (let j = 1; j <= val; j++) {
      let elem = "<td>" + i * j + "</td>";
      table += elem;
    }
    table += "</tr><tr>";
  }

  table += "</tr></table>";
  console.log(table);
  addTable.innerHTML = table;
}

