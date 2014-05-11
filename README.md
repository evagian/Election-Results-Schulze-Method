Έκδοση Αποτελεσμάτων Εκλογών
============================

Σκοπός της εργασίας είναι η συγγραφή προγραμμάτων σε γλώσσα Java για
την έκδοση αποτελεσμάτων εκλογών σύμφωνα με τη μέθοδο Schulze.

Η εργασία είναι προσωπική.

Κάθε φοιτητής θα εργαστεί στο προσωπικό του αποθετήριο στο GitHub. Για
να αξιολογηθεί μια εργασία θα πρέπει να πληροί τις παρακάτω
προϋποθέσεις:

1. Όλη η εργασία θα πρέπει να βρίσκεται σε έναν κατάλογο
  ``assignment-3`` μέσα στο αποθετήριο του φοιτητή.

2. Ο πηγαίος κώδικας του προγράμματος που θα γραφτεί θα πρέπει να βρίσκεται
  σε έναν υποκατάλογο ``src`` του καταλόγου ``assignment-3``.

3. Για τη συγγραφή του κώδικα απαιτείται η χρήση της βιβλιοθήκης
   [json.jar](https://github.com/dmst-algorithms-course/assigmnent-3/blob/master/json.jar)
   η οποία θα πρέπει να τοποθετηθεί σε έναν υποκατάλογο ``lib``
   του καταλόγου ``assignment-3``.
   Το αρχείο ``json.jar`` είναι η μεταγλωττισμένη βιβλιοθήκη JSON από το
   [JSON.org](http://www.json.org/java/)

4. Ο μεταγλωττισμένος κώδικας του προγράμματος που θα γραφτεί θα
  πρέπει να βρίσκεται σε έναν υποκατάλογο ``bin`` του καταλόγου
  ``assignment-2``. Έτσι, αν το αποθετήριο του φοιτητή είναι το
  ``example-repo``, η δομή των καταλόγων θα είναι:
    ```
    example-repo
        assignment-3
            src
            lib
            bin
    ```
5. Το πρόγραμμα θα πρέπει να έχει όνομα ``Schulze``.

6. Το πρόγραμμα θα πρέπει να εκτελείται ως εξής:
    ``` 
    java Schulze example_elections.json
    ```
    Η έξοδος θα πρέπει είναι της μορφής:
    ```
    a = 1 [c]
    b = 2 [a, c]
    c = 0 []
    d = 3 [a, b, c]    
    ```
    Το οποίο σημαίνει ότι ο υποψήφιος d επικρατεί επί τριών άλλων υποψηφίων,
    που παρατίθενται στη συνέχεια, ο υποψήφιος b επικρατεί επί δύο
    άλλων υποψηφίων, ο υποψήφιος a επικρατεί
    επί ενός άλλου υποψηφίου, και ο υποψήφιος c δεν επικρατεί έναντι κανενός
    υποψηφίου.
    
6. Τα αρχεία που θα δίνονται στον πρόγραμμα θα έχουν την εξής μορφή:
   ```
   {
       "candidates": [
           "a", "b", "c", "d"
       ],
       "ballots": [
           [0, 2, 3, 1],
           [0, 2, 3, 1],
           [0, 2, 3, 1],
           [0, 2, 3, 1],
           [0, 2, 3, 1],
           [0, 2, 3, 1],

           [1, 0, 3, 2],
           [1, 0, 3, 2],
           [1, 0, 3, 2],
           [1, 0, 3, 2],
        
           [2, 3, 1, 0],
           [2, 3, 1, 0], 
           [2, 3, 1, 0],

           [3, 1, 0, 2],
           [3, 1, 0, 2], 
           [3, 1, 0, 2],
           [3, 1, 0, 2],        

           [3, 2, 1, 0],
           [3, 2, 1, 0],        
           [3, 2, 1, 0],
           [3, 2, 1, 0]
       ]
    }
   
Αν μια εργασία δεν ικανοποιεί τις παραπάνω απαιτήσεις ***δεν θα είναι
δυνατή η αξιολόγησή της***. Επιβεβαιώστε λοιπόν ότι πράγματι το
πρόγραμμά σας μπορεί να κληθεί ***ακριβώς*** με τις εντολές που δίνονται
παραπάνω, και ότι παράγει ***ακριβώς*** την έξοδο που περιγράφεται.

Ο μεταγλωττισμός των αρχείων σας θα γίνεται με μία εντολή της μορφής:

    ```
    javac -cp ".:../lib/json.jar" *.java
    ```

Αντίστοιχα, η εκτέλεση του προγράμματός σας θα πρέπει να γίνεται με την εντολή:

    ```
    java -cp ".:../lib/json.jar" Schulze example_elections.json
    ```

Τις εντολές αυτές τις τρέχετε στον κατάλογο ```src```.
Προσέξτε την τελεία στις παραπάνω εντολές, είναι απαραίτητη προκειμένου να 
συμπεριληφθεί και ο κατάλογος που βρίσκεστε στα μονοπάτια αναζήτησης
κλάσεων (classpath) της Java: η τελεία αντιστοιχεί στον τρέχοντα κατάλογο.
Αντίστοιχα, οι δύο τελείες (στο ```../lib/json/jar```) αντιστοιχούν στον
πατέρα του τρέχοντα καταλόγου και είναι απαραίτητες προκειμένου
να βρούμε από τον τρέχοντα κατάλογο ```src``` τον κατάλογο ```lib```.

Στο λειτουργικό σύστημα MS-Windows
χρησιμοποιείται ο χαρακτήρας ```;``` αντί του χαρακτήρα ```:``` για
τον διαχωρισμό των μονοπατιών.

Για να ελέγξετε το πρόγραμμά σας μπορείτε να χρησιμοποιήσετε τα αρχεία:

* [example_elections.json](https://github.com/dmst-algorithms-course/assigmnent-3/blob/master/example_elections.json)

* [schulze_1.json](https://github.com/dmst-algorithms-course/assigmnent-3/blob/master/schulze_1.json)

* [example_elections_large.json](https://raw.githubusercontent.com/dmst-algorithms-course/assigmnent-3/master/example_elections_large.json)

Στο τελευταίο αρχείο τα αποτελέσματα θα πρέπει να είναι (με ενδεχομένως διαφορετική διάταξη των ονομάτων στην έξοδο):

```
Faustus Sergius Caudex = 10 [Pius Valerius Blasio, Rufinus Lunius Purpureo, Alpinus Sulpicious Fullo, Ducenius Tarquinius Centho, Ericus Vanus Derlindenus, Vibulius Camilius Glabrio, Proculus Galerius Sura, Julius Aurelius Longus, Marcus Calpurnius Maximus, Spartacus Locundus Ludens]
Italicus Curtius Nerva = 15 [Faustus Sergius Caudex, Pius Valerius Blasio, Rufinus Lunius Purpureo, Alpinus Sulpicious Fullo, Claudius Nonious Salinator, Ducenius Tarquinius Centho, Marilinus Lenus Menus, Ericus Vanus Derlindenus, Vibulius Camilius Glabrio, Proculus Galerius Sura, Severus Marcius Rex, Gaius Antonius Scipio, Julius Aurelius Longus, Marcus Calpurnius Maximus, Spartacus Locundus Ludens]
Pius Valerius Blasio = 7 [Rufinus Lunius Purpureo, Ducenius Tarquinius Centho, Ericus Vanus Derlindenus, Vibulius Camilius Glabrio, Proculus Galerius Sura, Julius Aurelius Longus, Marcus Calpurnius Maximus]
Rufinus Lunius Purpureo = 4 [Ericus Vanus Derlindenus, Vibulius Camilius Glabrio, Julius Aurelius Longus, Marcus Calpurnius Maximus]
Alpinus Sulpicious Fullo = 8 [Pius Valerius Blasio, Rufinus Lunius Purpureo, Ducenius Tarquinius Centho, Ericus Vanus Derlindenus, Vibulius Camilius Glabrio, Proculus Galerius Sura, Julius Aurelius Longus, Marcus Calpurnius Maximus]
Claudius Nonious Salinator = 11 [Faustus Sergius Caudex, Pius Valerius Blasio, Rufinus Lunius Purpureo, Alpinus Sulpicious Fullo, Ducenius Tarquinius Centho, Ericus Vanus Derlindenus, Vibulius Camilius Glabrio, Proculus Galerius Sura, Julius Aurelius Longus, Marcus Calpurnius Maximus, Spartacus Locundus Ludens]
Ducenius Tarquinius Centho = 5 [Ericus Vanus Derlindenus, Vibulius Camilius Glabrio, Proculus Galerius Sura, Julius Aurelius Longus, Marcus Calpurnius Maximus]
Marilinus Lenus Menus = 12 [Faustus Sergius Caudex, Pius Valerius Blasio, Rufinus Lunius Purpureo, Alpinus Sulpicious Fullo, Claudius Nonious Salinator, Ducenius Tarquinius Centho, Ericus Vanus Derlindenus, Vibulius Camilius Glabrio, Proculus Galerius Sura, Julius Aurelius Longus, Marcus Calpurnius Maximus, Spartacus Locundus Ludens]
Ericus Vanus Derlindenus = 2 [Vibulius Camilius Glabrio, Julius Aurelius Longus]
Vibulius Camilius Glabrio = 0 []
Eurycles Curtius Piso = 16 [Faustus Sergius Caudex, Italicus Curtius Nerva, Pius Valerius Blasio, Rufinus Lunius Purpureo, Alpinus Sulpicious Fullo, Claudius Nonious Salinator, Ducenius Tarquinius Centho, Marilinus Lenus Menus, Ericus Vanus Derlindenus, Vibulius Camilius Glabrio, Proculus Galerius Sura, Severus Marcius Rex, Gaius Antonius Scipio, Julius Aurelius Longus, Marcus Calpurnius Maximus, Spartacus Locundus Ludens]
Proculus Galerius Sura = 4 [Ericus Vanus Derlindenus, Vibulius Camilius Glabrio, Julius Aurelius Longus, Marcus Calpurnius Maximus]
Quintus Cassius Elva = 17 [Faustus Sergius Caudex, Italicus Curtius Nerva, Pius Valerius Blasio, Rufinus Lunius Purpureo, Alpinus Sulpicious Fullo, Claudius Nonious Salinator, Ducenius Tarquinius Centho, Marilinus Lenus Menus, Ericus Vanus Derlindenus, Vibulius Camilius Glabrio, Eurycles Curtius Piso, Proculus Galerius Sura, Severus Marcius Rex, Gaius Antonius Scipio, Julius Aurelius Longus, Marcus Calpurnius Maximus, Spartacus Locundus Ludens]
Severus Marcius Rex = 13 [Faustus Sergius Caudex, Pius Valerius Blasio, Rufinus Lunius Purpureo, Alpinus Sulpicious Fullo, Claudius Nonious Salinator, Ducenius Tarquinius Centho, Marilinus Lenus Menus, Ericus Vanus Derlindenus, Vibulius Camilius Glabrio, Proculus Galerius Sura, Julius Aurelius Longus, Marcus Calpurnius Maximus, Spartacus Locundus Ludens]
Gaius Antonius Scipio = 10 [Pius Valerius Blasio, Rufinus Lunius Purpureo, Alpinus Sulpicious Fullo, Ducenius Tarquinius Centho, Ericus Vanus Derlindenus, Vibulius Camilius Glabrio, Proculus Galerius Sura, Julius Aurelius Longus, Marcus Calpurnius Maximus, Spartacus Locundus Ludens]
Julius Aurelius Longus = 1 [Vibulius Camilius Glabrio]
Marcus Calpurnius Maximus = 3 [Ericus Vanus Derlindenus, Vibulius Camilius Glabrio, Julius Aurelius Longus]
Spartacus Locundus Ludens = 8 [Pius Valerius Blasio, Rufinus Lunius Purpureo, Ducenius Tarquinius Centho, Ericus Vanus Derlindenus, Vibulius Camilius Glabrio, Proculus Galerius Sura, Julius Aurelius Longus, Marcus Calpurnius Maximus]
```

