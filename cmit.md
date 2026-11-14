# Computer Science & Programming Interview Q&A

---

## 1. Stack (LIFO - Last In, First Out)

### **Q1. Stack ka bunyadi usool kya hai aur is ke main operations kaun se hain?**
**Jawab:** Yeh **LIFO** (jo aakhir mein aayega, woh pehle niklega) ke usool par kaam karta hai. Is ke main operations darj zail hain:
* **Push:** Oopar data dalna.
* **Pop:** Oopar se data nikalna.
* **Peek/Top:** Bina nikale sab se oopar wala element dekhna.

> *Note: Yeh tamam operations $O(1)$ time complexity mein kaam karte hain.*

### **Q2. Stack ke real-world aur programming mein kya istemalat hain?**
**Jawab:** 
* Text editors mein **Undo/Redo** feature.
* Web browser ki **back-button history**.
* Function calls ko manage karna (**Call Stack**).
* Code mein brackets ka balance check karna.

### **Q3. Do Stacks ka istemal karte hue ek Queue kaise banayi jati hai?**
**Jawab:** 
* **Enqueue (Data dalna):** `Stack1` mein Push karein.
* **Dequeue (Data nikalna):** Agar `Stack2` khali ho, toh `Stack1` se sare elements nikal kar `Stack2` mein dal dein (jis se tarteeb ulti ho jayegi) aur phir `Stack2` se Pop kar lein.

### **Q4. Stack Overflow aur Stack Underflow se kya murad hai?**
**Jawab:** 
* **Stack Overflow:** Tab hota hai jab aap pehle se bhare hue stack mein mazeed data dalne ki koshish karein (aksar *infinite recursion* ki wajah se).
* **Stack Underflow:** Tab hota hai jab aap khali stack se data nikalne ki koshish karein.

### **Q5. Aisa Stack kaise design karein jo $O(1)$ time mein sab se chota element (Minimum) bataye?**
**Jawab:** Main stack ke sath ek extra **Min-Stack** rakhein jo har step par mojooda sab se choti value (Minimum value) ka record rakhta hai.

---

## 2. Queue (FIFO - First In, First Out)

### **Q6. Normal Queue aur Circular Queue mein kya farq hai?**
**Jawab:** 
* **Normal Queue:** Array-based queue mein data nikalne ke baad khali hone wali jagah zaya ho jati hai kyunki `front` pointer aage barh jata hai.
* **Circular Queue:** Is mein aakhri sira dobara pehle sire se jura hota hai, jis se khali jagah dobara istemal ho jati hai.

### **Q7. Priority Queue kya hai aur ise kaise banaya jata hai?**
**Jawab:** Aisi queue jis mein har element ki ek priority hoti hai, aur zyada priority wale element ko pehle process kiya jata hai chahe woh baad mein aaya ho. Ise aam taur par **Binary Heap** ke zariye banaya jata hai ($O(\log n)$ time).

### **Q8. Deque (Double-Ended Queue) kya hai?**
**Jawab:** Yeh ek khas qism ki queue hai jis mein data ko `front` aur `rear` dono siron se $O(1)$ time mein dala aur nikala ja sakta hai.

### **Q9. Computer science mein Queue kahan istemal hoti hai?**
**Jawab:** 
* CPU task scheduling.
* Printer ki qatar (**Spooling**).
* Web server par aane wali requests ko handle karne mein.
* Graph mein **BFS (Breadth-First Search)** algorithm mein.

### **Q10. Stack aur Queue mein bunyadi structural farq kya hai?**
**Jawab:** Stack mein data dalne aur nikalne ke liye sirf **ek sira (`Top`)** istemal hota hai (LIFO), jabke Queue mein **do sire** istemal hote hain—dalne ke liye `Rear` aur nikalne ke liye `Front` (FIFO).

---

## 3. Linked List

### **Q11. Array aur Linked List mein se kis ka intekhab kab karna chahiye?**
**Jawab:** 
* **Array:** Agar aap ko tez random access ($O(1)$ indexing) chahiye toh Array behtar hai.
* **Linked List:** Agar aap ko bar bar data insert ya delete karna hai aur memory ka size pehle se maloom nahi toh Linked List behtar hai.

### **Q12. Linked List mein loop ya cycle ka pata kaise lagaya jata hai?**
**Jawab:** **Floyd’s Cycle-Finding Algorithm** (kachua aur khargosh ka tareeqa) istemal karein. Ek `slow` pointer ko 1 qadam aur `fast` pointer ko 2 qadam aage barhayein; agar dono ek jagah mil jayein toh list mein cycle mojood hai.

### **Q13. Ek hi chakkar (Single Pass) mein Linked List ka darmiyani (Middle) element kaise maloom karein?**
**Jawab:** Do pointers (`slow` aur `fast`) istemal karein. `slow` ko 1 qadam aur `fast` ko 2 qadam chalayein; jab `fast` aakhir mein pahunchega toh `slow` bilkul darmiyan mein hoga.

### **Q14. Singly Linked List aur Doubly Linked List mein kya farq hai?**
**Jawab:** 
* **Singly Linked List:** Har node sirf agle node (`next`) ka pata rakhta hai (ek taraf safar).
* **Doubly Linked List:** Agle (`next`) aur pichle (`previous`) dono nodes ka pata hota hai, jis se dono taraf safar aasan hota hai lekin memory zyada kharch hoti hai.

### **Q15. Singly Linked List ko ulta (Reverse) kaise kiya jata hai?**
**Jawab:** Teen pointers (`prev`, `curr`, `next`) ka istemal karte hue list mein se guzrein aur har node ke `next` pointer ka rukh mor kar pichle node (`prev`) ki taraf kar dein.
* **Time Complexity:** $O(n)$
* **Space Complexity:** $O(1)$

---

## 4. SQL Basics

### **Q16. `WHERE` aur `HAVING` clause mein kya farq hai?**
**Jawab:** 
* **`WHERE`:** Grouping (`GROUP BY`) se pehle individual rows ko filter karta hai.
* **`HAVING`:** Group banne aur aggregate functions (`COUNT`, `SUM`) lagne ke baad data ko filter karta hai.

### **Q17. `DELETE`, `TRUNCATE`, aur `DROP` mein farq wazeh karein.**
**Jawab:** 
* **`DELETE`:** Khas rows ko hatata hai aur ise wapas (**Rollback**) kiya ja sakta hai.
* **`TRUNCATE`:** Poore table ki tamam rows tezi se khali kar deta hai.
* **`DROP`:** Poore table ke structure aur data ko hamesha ke liye khatam kar deta hai.

### **Q18. `INNER JOIN` aur `LEFT JOIN` mein kya farq hai?**
**Jawab:** 
* **`INNER JOIN`:** Dono tables se sirf wahi data lata hai jo aapas mein match ho raha ho.
* **`LEFT JOIN`:** Bayein (left) table ka sara data lata hai aur dayein (right) table se sirf match hone wala data (agar match na ho toh `NULL`) dikhata hai.

### **Q19. Primary Key aur Foreign Key kya hoti hain?**
**Jawab:** 
* **Primary Key:** Table ke har record ki munfarid (unique) pehchan hoti hai aur yeh khali (`NULL`) nahi ho sakti.
* **Foreign Key:** Ek table ka woh column hai jo doosre table ki Primary Key se jura hota hai taake data ka rabt barqarar rahe.

### **Q20. `UNION` aur `UNION ALL` mein kya farq hai?**
**Jawab:** 
* **`UNION`:** Do queries ke results ko jorta hai aur duplicate rows ko hata deta hai (yeh thora slow hota hai).
* **`UNION ALL`:** Tamam data ko bina duplicate hataye jor deta hai (yeh tez hota hai).

---

## 5. HTTP (HyperText Transfer Protocol)

### **Q21. `GET` aur `POST` methods mein kya farq hai?**
**Jawab:** 
* **`GET`:** Server se data mangwane ke liye istemal hota hai aur is ka data URL mein nazar aata hai.
* **`POST`:** Server par naya data bhejne ke liye istemal hota hai jis mein data **Request Body** mein chupa hota hai (yeh sensitive data ke liye mehfooz hai).

### **Q22. `PUT` aur `PATCH` mein kya farq hai?**
**Jawab:** 
* **`PUT`:** Kisi record ko mukammal taur par naye data se badal deta hai.
* **`PATCH`:** Record mein juzwi tabdeeli (sirf khas fields ko update) karne ke liye istemal hota hai.

### **Q23. "HTTP ek Stateless protocol hai" ka kya matlab hai?**
**Jawab:** Is ka matlab hai ke har HTTP request azaad hoti hai aur server ko pichli requests ka koi record yaad nahi rehta. User ki pehchan barqarar rakhne ke liye **Cookies**, **Sessions**, ya **Tokens** (jaise JWT) istemal kiye jate hain.

### **Q24. HTTP Status Codes ki ahem categories kaun si hain?**
**Jawab:** 
* **`2xx` (Kamyabi):** `200 OK`, `201 Created`
* **`3xx` (Redirection):** `301 Moved`
* **`4xx` (Client ki ghalti):** `400 Bad Request`, `401 Unauthorized`, `404 Not Found`
* **`5xx` (Server ki kharabi):** `500 Internal Server Error`

### **Q25. HTTP aur HTTPS mein kya farq hai?**
**Jawab:** 
* **HTTP:** Data ko saada text (Plain text) mein bhejta hai jise hack kiya ja sakta hai.
* **HTTPS:** Data ko **SSL/TLS** ke zariye encrypt (mehfooz) kar ke bhejta hai jis se data chori ya tabdeel hone ka khatra nahi rehta.