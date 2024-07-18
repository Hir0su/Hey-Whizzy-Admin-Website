![Uploading whizzy1.png…]()

# Hey-Whizzy-Admin-Website
[Hey Whizzy](https://github.com/Hir0su/Hey-Whizzy)'s Admin website Repository

## Installation Guide before deploying

### For Search feature

### Installation for Search
```
Install these libraries first
```
- pip install nltk
- pip install scikit-learn

### Search Preparation
- Create new file
- Name it install.py
- Run this script
```
import nltk
nltk.download('punkt')
nltk.download('stopwords')
```
- This is a required data for the library nltk
- This will download the necessary data for tokenization and stop word removal.

### Final Piece
- Create a new file, call it text_preprocessing.py
- Call this on your initialize.py or app.py
```
from nltk.tokenize import word_tokenize
from nltk.corpus import stopwords
from nltk.stem import PorterStemmer

def preprocess_text(text):
    # Tokenize the text into words
    tokens = word_tokenize(text.lower())

    # Remove stop words
    stop_words = set(stopwords.words('english'))
    filtered_tokens = [w for w in tokens if not w.lower() in stop_words]

    # Perform stemming
    stemmer = PorterStemmer()
    stemmed_tokens = [stemmer.stem(w) for w in filtered_tokens]

    # Join the stemmed tokens back into a string
    preprocessed_text = ' '.join(stemmed_tokens)

    return preprocessed_text
```

## For flask

### Installation of Flask
```
pip install flask
pip install Flask-MySQLdb
pip install werkzeug
pip install Flask-Mail
```

### Server preparation
- Run xampp
- Run raspi_flask.py

### Changes made for flask to work on the network

- Run xampp with administrator mode.
- Allow python on the firewall (on searchbar "allow").
- Change code on app.run(debug=True, host='0.0.0.0').
- Make sure all devices (to be used) are connected on the same network.
