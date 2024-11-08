## Aplikacja FastAPI do Predykcji Rezygnacji Klienta

## Opis projektu

Aplikacja FastAPI, która przewiduje prawdopodobieństwo rezygnacji klienta na podstawie danych o subskrypcji i historii użytkowania. Wyniki wyświetlane są na podstawie modelu uczenia maszynowego, wczytanego z pliku model_random_forest.pkl.

## Wymagania

- Python 3.7 lub nowszy,
- FastAPI,
- Uvicorn==0.22.0,
- scikit-learn==1.5.2,
- joblib==1.4.2,
- numpy==1.26.4,
- pandas==2.2.2,
- python-multipart,
- jinja2==3.1.2 (do szablonów HTML).

## Instalacja

1. Sklonuj repozytorium:

   git clone https://github.com/Kiniaka/DataScienceGroupProject.git

2. Wejdz w comend line do odpowiedniego katalogu:

   cd DataScienceGroupProject

3. Zainstaluj wymagane pakiety:

   pip install -r requirements.txt

## Uruchamianie aplikacji

1. Upewnij się, że serwer jest uruchomiony w środowisku zdefiniowanym w `.env`.
2. Uruchom aplikację za pomocą Uvicorn:
    ```bash
    uvicorn main:app --reload --port 8000
lub"
    docker-compose up --build"        
    ```

3. Otwórz przeglądarkę i przejdź na adres: [http://127.0.0.1:8000/form].

## Użycie
- Wprowadź dane klienta w formularzu dostępnym pod `/form`.
- Po przesłaniu danych wyświetli się prawdopodobieństwo pozostania (`probability_stay`) oraz prawdopodobieństwo rezygnacji (`probability_churn`).

## Zmienne środowiskowe
Zdefiniuj zmienne środowiskowe w pliku `.env` zgodnie z poniższym wzorcem:
```dotenv
MODEL_PATH=model_random_forest.pkl
PORT=8000
DEBUG=True


Umieść model model_random_forest.pkl w katalogu projektu. Plik ten powinien zawierać wytrenowany model Random Forest oraz skaler, zapisany w formacie:

{'model': trained_model, 'scaler': scaler}

Upewnij się, że plik .env zawiera wymagane zmienne środowiskowe
