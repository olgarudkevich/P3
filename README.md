# P3

**Виконала:** Студентка групи 4СОМ, Рудкевич Ольга 

**Практична робота №3**

**Тема: Реалізаця двозв'язних списків. Контейнер list**  

**Мета роботи:**
Ознайомитися з концепцією зв'язних списків та стандартним контейнером std::list у C++, навчитися ефективно використовувати його для виконання базових операцій вставки, видалення, модифікації та пошуку елементів за допомогою ітераторів.   

**Завдання:**

<img width="710" height="149" alt="image" src="https://github.com/user-attachments/assets/54864e0b-057b-4591-b05a-42823915fb0d" />

<img width="716" height="445" alt="image" src="https://github.com/user-attachments/assets/7c8ab9f6-47f8-466e-8f52-2e7fba8488c5" />


**Програмний код:**
1	#include <iostream>
2	#include <list>
3	
4	using namespace std;
5	
6	void printList(list<double>& lst) {
7	    for (auto it = lst.begin(); it != lst.end(); ++it) {
8	        cout << *it << " ";
9	    }
10	    cout << endl;
11	}
12	
13	void printListReverse(list<double>& lst) {
14	    for (auto rit = lst.rbegin(); rit != lst.rend(); ++rit) {
15	        cout << *rit << " ";
16	    }
17	    cout << endl;
18	}
19	
20	int main() {
21	    list<double> myList = {5.5, 12.4, 19.8, 26.1, 8.7};
22	
23	    cout << "1. ";
24	    printList(myList);
25	
26	    myList.push_front(3.5);
27	    myList.push_back(30.5);
28	    myList.pop_front();
29	    
30	    cout << "2. ";
31	    printList(myList);
32	
33	    cout << "3. ";
34	    printListReverse(myList);
35	
36	    for (auto it = myList.begin(); it != myList.end(); ++it) {
37	        *it += 1.5;
38	    }
39	    
40	    cout << "4. ";
41	    printList(myList);
42	
43	    auto it = myList.begin();
44	    while (it != myList.end()) {
45	        if (*it > 25.0) {
46	            it = myList.erase(it);
47	        } else {
48	            if (*it < 10.0) {
49	                myList.insert(it, 10.0);
50	            }
51	            ++it;
52	        }
53	    }
54	    
55	    cout << "5. ";
56	    printList(myList);
57	
58	    double sum = 0.0;
59	    int count = 0;
60	    for (auto iter = myList.begin(); iter != myList.end(); ++iter) {
61	        if (*iter <= 15.0) {
62	            sum += *iter;
63	            count++;
64	        }
65	    }
66	    
67	    if (count > 0) {
68	        cout << "6. Avg (<= 15): " << (sum / count) << endl;
69	    }
70	    
71	    cout << "   Reverse: ";
72	    printListReverse(myList);
73	
74	    return 0;
75	}

**Результати виконання:**

<img width="495" height="198" alt="image" src="https://github.com/user-attachments/assets/24e89e90-3128-4d9a-917b-4204cb9bd01a" />

**Скріншоти роботи програми:**

<img width="1142" height="731" alt="image" src="https://github.com/user-attachments/assets/86e98680-eb2d-45c4-9a96-7cda832e5655" />

**Висновок:**

Під час виконання практичної роботи було успішно закріплено навички роботи з контейнером std::list стандартної бібліотеки шаблонів (STL) у C++. Було реалізовано структуру списку для дійсних чисел та відпрацьовано механізми перебору елементів за допомогою прямих (begin(), end()) та зворотних (rbegin(), rend()) ітераторів. На практиці застосовано базові методи модифікації списку: додавання елементів на початок та в кінець (push_front, push_back), видалення (pop_front, erase), а також вставка елементів на довільну позицію (insert). Усі завдання 12-го варіанту виконано коректно, програма працює без помилок і видає очікуваний результат.
