# DSPharmacy
## Οδηγίες λειτουργίας
### Εγκατάσταση
1. git clone https://github.com/cevassil/ErgasiaSept_E17024_VASILOPOULOS_KONSTANTINOS.git
2. sudo docker-compose up
3.  Επίσκεψη στο localhost:5000 από έναν web browser.

### Admin user info
| Username | email | password | category |
| ------------- | ------------- | ------------- | ------------- | 
| admin         | admin@dspharmacy.com | admin | admin |

### MongoDb data

 - users: [ 	{ 		"name": "admin", 		"email": "admin@dspharmacy.com",
   		"password": "admin", 		"ssn": 19037500856, 		"category": "admin" 	}
   ]
 - products: [ 	{ 		"name": "Depon Maximum", 		"description": "Αναβράζον
   Δισκίο Παρακεταμόλης", 		"price": 2, 		"category": "Αναλγητικά",
   		"stock": 5 	}, 	{ 		"name": "Salospir", 		"description": "Χάπια
   ασπιρίνης", 		"price": 1, 		"category": "Αναλγητικά", 		"stock": 9
   	}, 	{ 		"name": "Seractil", 		"description": "Χαπι
   δεξιβουπροφαίνης", 		"price": 6, 		"category": "Αντιφλεγμονώδες",
   		"stock": 5 	}, 	{ 		"name": "Cipralex", 		"description":
   "Αντικαταθλιπτικό φάρμακο που βοηθάει στην ομαλοποίηση των επιπέδων
   σεροτονίνης στον εγκέφαλο", 		"price": 15, 		"category":
   "Αντικαταθλιπτικά", 		"stock": 10 	} ]
 - ## Endpoints
 - ### Αρχική σελίδα
	#### Σύνδεση/ Εγγραφή
	#### Σύνδεση
	Εδώ ο χρήστης ή ο admin μπορούν να συνδεθουν στο σύστημα χρησιμοποιώντας το email και τον κωδικό πρόσβασης τους. Σε περίπτωση που ο κωδικός ή το email είναι λάθος εμφανίζεται αντίστοιχο μήνυμα. 
	#### Εγγραφή 
	Εδώ ο χρήστης μπορεί να δημιουργήσει λογαριασμό. Επιλέγει όνομα χρήστη, κωδικό 8-20 χαρακτήρων , το email του που θα χρησιμοποιηθεί και για την σύνδεση του στο σύστημα καθώς και το ΑΜΚΑ του. Σε περίπτωση που επιχειρίσει να βάλει ΑΜΚΑ που δεν είναι έγκυρος (ΗΗ> 31 και ΜΜ>12) εμφανίζεται αντίστοιχο μήνυμα. Μόλις εγγραφεί στο σύστημα γίνεται αυτόματα redirect στην σελίδα **Σύνδεση** για να μπει στο σύστημα.
	
 - ### Σύνδεση / Χρήστης 
	####  Αρχική
	Εδώ ο χρήστης βλέπει σε λίστα όλα τα αντικείμενα που είναι διαθέσιμα προς αγορά απο το φαρμακείο και έχει την επιλογή αναζήτησης προϊόντος μέσω του ονόματός του και να προσθέσει προϊόντα στο καλάθι του. Επίσης στην μπάρα πλοήγησης έχει την επιλογή να δει το καλάθι του, το ιστορικό των παραγγελιών του, να διαγραφεί από το σύστημα και να κάνει αποσύνδεση.
	#### Αναζήτηση 
	Εφόσον ο χρήστης κάνει αναζήτηση το προϊόν που θέλει έχει την επιλογή να το προσθέσει στο καλάθι ή να εκτελέσει μια από τις προαναφερθέντες ενέργειες στην μπάρα πλοήγησης.
	#### Καλάθι
	Όταν ο χρήστης πατήσει να πάει στο **Καλάθι** αν το καλάθι του είναι άδειο εμφανίζεται μήνυμα καθώς και ενας σύνδεσμος για την **Αρχική** σελίδα ώστε να προσθέσει προϊόντα. Εφόσον προσθέσει ένα προϊον στο καλάθι του είτε από την **Αρχική** είτε από την **Αναζήτηση** ανακατευθύνεται αυτόματα στο **Καλάθι** για να δεί τα προϊόντα που έχει προσθέσει. Εκεί πλέον έχει την επιλογή να αφαιρέσει ένα προϊον από το καλάθι είτε να προχωρήσει στην αγορά των προϊόντων. 
	#### Αγορά
	Εφόσον ο χρήστης επιλέξει να αγοράσει τα προϊόντα από το καλάθι κατευθύνεται στην σελίδα **Αγορά** όπου του αναφέρονται τα προϊοντα που έχει στο καλάθι του καθώς και το κόστος των προϊόντων που έχουν επιλεγεί. Εδώ μπορεί είτε να πάει πίσω και να προσθέσει/αφαιρέσει στοιχεία πηγαίνοντας στην **Αρχική** ή στο ** Καλάθι ** είτε βάζει τον 16ψήφιο κωδικό της κάρτας του και ολοκληρωνεί την παραγγελία του. 
	#### Ιστορικό Παραγγελίων
	Αν ο χρήστης επισκεφτεί την σελίδα προτού αγοράσει κάποιο προϊον εμφανίζεται σύνδεσμος για την **Αρχική** σελίδα ώστε να αγοράσει κάτι. Αλλίως αφού ολοκληρώσει την παραγγελία του στην σελίδα **Αγορά** ανακατευθύνεται στην σελίδα αυτή και εμφανίζονται κατα χρονολογική σειρά οι παραγγελίες του με σειρά από την παλαιότερη και κατεβαίνοντας στις νεότερες.
	#### Διαγραφή Χρήστη
	Επιλέγοντας **Διαγραφή Χρήστη** ο χρήστης αφαιρείται απευθείας από το σύστημα και ανακατευθύνεται στην σελίδα **Σύνδεση**.
	#### Αποσύνδεση
	Επιλέγοντας **Αποσύνδεση** ο χρήστης αποσυνδέεται από το σύστημα . Η ενέργεια αυτή επίσης αδείαζει το καλάθι του χρήστη. 
	**Σε περίπτωση που το απόθεμα ενός προϊοντος μηδενιστεί το προϊον αφαιρείται από την λίστα και ο χρήστης δεν μπορεί πλέον να το επιλέξει για αγορά.**
 - ### Σύνδεση / Admin
   #### Αρχική
   Στην αρχική σελίδα ο Διαχείριστης μπορεί μέσω της μπάρας πλοήγησης να επιλέξει **Προσθήκη Προϊόντων** , **Διαγραφή Προϊόντων**, **Διαχείριση Προϊόντων** και **Αποσύνδεση**.
   #### Προσθήκη προϊόντων
   Εδώ ο Διαχειριστής προσθέτει νέα προϊόντα στην βάση συμπληρώνοντας αντίστοιχα τα πεδία. Μόλις εισάγει όλα τα στοιχεία πατώντας προσθήκη στην βάση καταχωρούνται τα στοιχεία.
   #### Διαγραφή προϊόντων
   Εδώ ο Διαχειριστής διαγράφει προϊόντα βάση του id τους στην βάση. Εμφανίζονται όλα τα προϊόντα σε μια λίστα και κάνοντας copy και paste το id τους στο πεδίο αφαιρούνται πλήρως από την βάση. (*-Σε περίπτωση που εισαγεί λανθασμένα το id εμφανίζεται ενα debug error. Πατώντας το κουμπί για να πάμε στην προηγούμενη σελίδα και πληκτρολογόντας/αντιγράφοντας σωστά τον κωδικό πραγματοποιείται επιτυχώς η διαγραφή.-)*
   #### Διαχείριση προϊόντων
   Εδώ ο Διαχείριστής μπορεί μέσω του id του προϊόντος να ενημερώσει τα στοιχεία του στην βάση. Τα προηγούμενα στοιχεία έρχονται προ συμπληρωμένα στα πεδία με την αντίστοιχη σειρά: Όνομα | Κατηγορία | Απόθεμα | Περιγραφή Προϊόντος | Τιμή . Εφόσον κάνει τις επιθυμητές αλλαγές πατώντας το κουμπί ενημέρωση βάσης οι αλλαγές καταχωρούνται στην βάση και πραγματοποιείται ανακατεύθυνση στην σελίδα επιλογής προϊόντων προς ενημέρωση. (*-Σε περίπτωση που εισαγεί λανθασμένα το id εμφανίζεται ενα debug error. Πατώντας το κουμπί για να πάμε στην προηγούμενη σελίδα και πληκτρολογόντας/αντιγράφοντας σωστά τον κωδικό πραγματοποιείται επιτυχώς η επιλογή του προϊόντος προς ενημέρωση.-)*
   #### Αποσύνδεση
   Τέλος επιλέγοντας αποσύνδεση ο Διαχειρίστης αποσυνδέεται από το σύστημα και επιστρέφει στην σελίδα **Σύνδεση**.
