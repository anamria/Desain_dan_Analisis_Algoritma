**Ana Maria Parasanti - 2110131320009**

---

### Time Complexity

*Time Complexity* adalah seberapa lama waktu yang diperlukan untuk menjalankan suatu algoritma.

*Time Complexity Analysis* adalah suatu cara sederhana untuk mengetahui berapa lama waktu yang dibutuhkan untuk menjalankan suatu algoritma dengan input tertentu (n).

### Big-O Notasi

*Big-O Notation* adalah cara untuk mengkonversi keseluruhan langkah-langkah suatu algoritma kedalam bentuk Aljabar, yaitu dengan menghiraukan
konstanta yang lebih kecil dan koefisien yang tidak berdampak besar terhadap keseluruhan kompleksitas permasalahan yang diselesaikan oleh algoritma tersebut.

Contoh:

    Regular       Big-O

    2             O(1)   --> It's just a constant number

    2n + 10       O(n)   --> n has the largest effect

    5n^2          O(n^2) --> n^2 has the largest effect

Terdapat beberapa macam time complexity, diantaranya:

+ O(1) — Constant Time

    *Constant Time* artinya banyaknya input yang diberikan kepada sebuah algoritma, tidak akan mempengaruhi waktu proses (runtime) dari algoritma tersebut.

        let myArray = [1, 5, 0, 6, 1, 9, 9, 2];
        function getFirst(input){
        return input[0]; // selalu melakukan 1 langkah
        }
        let firstEl = getFirst(myArray);
    
    Contoh diatas, terdapat sebuah fungsi untuk mengambil elemen pertama dari sebuah input array. Kita bisa melihat bahwa berapapun jumlah array yang 
    diberikan kepada fungsi tersebut, dia akan selalu melakukan 1 hal, yaitu mengambil elemen pertama. Itu artinya jumlah input yang diberikan tidak 
    mempengaruhi waktu proses (runtime) dari algoritma tersebut.
    
    Waktu *runtime* pada *Constant Time*:
    
    ![DAA1](https://user-images.githubusercontent.com/112605121/191743585-0b49eaac-c1bb-44b2-ad9e-32dd67198fb7.png)

+ O(log n) — Logarithmic Time

    *Logarithmic Time* artinya ketika kita memberikan input sebesar n terhadap sebuah fungsi, jumlah tahapan yang dilakukan oleh fungsi tersebut berkurang 
    berdasarkan suatu faktor.

    *Binary Search* adalah algoritma yang kita gunakan dalam mencari posisi nilai dari suatu array dengan cara ‘mengeliminasi’ setengah dari array input 
    untuk mempercepat proses pencarian.

        let sortedArray = [11, 24, 30, 43, 51, 61, 73, 86];
        function isExists(number, array){
            var midPoint = Math.floor( array.length /2 );
            if( array[midPoint] === num) return true;
            let isFirstHalf = false;
            if( array[midPoint] < num ) isFirstHalf = true;
        
            else if( array[midpoint] > num ) isFirstHalf = false;
            if (array.length == 1) return false;
            else { 
                // memanggil fungsi yang sama dengan mengeleminiasi setengah dari input array
                if (isFirstHalf) 
                    return isExists(number, getFirstHalf(array));
                else 
                    return isExists(number, getSecondHalf(array));
            }
        }
        isExists (24, sortedArray); // return true
        isExists (27, sortedArray); // return false
    
+ O(n) — Linear Time

    *Linear Time* adalah ketika runtime dari fungsi kita berbanding lurus dengan jumlah input yang diberikan. Jadi, jika semakin banyak jumlah 
    input yang diberikan, maka waktu proses/runtime dari fungsi tersebut akan semakin besar.

        let myArray = [1, 5, 0, 6, 1, 9, 9, 2];
        function getMax(input){
            var max = 0;
            for (var i=0; i<input.length; i++){
                if (max < input[i])
                    max = input[i];
            }
            return max;
        }
        let maxNumber = getMax(myArray);
    
    Waktu *runtime* pada *Linear Time*:
    
    ![DAA1 2](https://user-images.githubusercontent.com/112605121/191743828-7fb01f26-6e47-455b-bf1f-8947ccf8c5f6.png)

+ O(n²) — Quadratic Time

    *Quadratic Time* adalah ketika runtime dari fungsi kita adalah sebesar n^2, dimana n adalah jumlah input dari fungsi tersebut. Hal tersebut bisa terjadi 
    karena kita menjalankan fungsi linear didalam fungsi linear (n*n).

        let myArray = [1, 5, 0, 6, 1, 9, 9, 2];
        function sort(input){
            var sortedArray = [];
            for (var i=0; i<input.length; i++){ // O(n)
                let min = input[i];
                for (var j=i+1; i<input.length; i++){ // O(n)
                    if (input[i] < input[j])
                        min = input[j];
                }
                sortedArray.push(min);
            }
            return sortedArray;
        }
        let sortedArray = sort(myArray);
    
    Waktu *runtime* pada *Quadratic Time*:
    
    ![DAA1 3](https://user-images.githubusercontent.com/112605121/191743903-a7ca3ee0-5104-4243-9f7d-7362d3a0c5db.png)

+ O(2^n) — Exponential Time

    *Exponential Time* biasanya digunakan dalam situasi dimana kita tidak terlalu tahu terhadap permasalahan yang dihadapi, sehingga mengharuskan kita mencoba 
    setiap kombinasi dan permutasi dari semua kemungkinan.
    
    Waktu *runtime* pada *Exponential Time*:
    
    ![DAA1 4](https://user-images.githubusercontent.com/112605121/191743950-30fe959d-9d0f-4609-90fc-2dc767b7d502.png)

---
