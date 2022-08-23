# Memo

## Formation LinkedIn

C:\users\<user>\datascience

Py -3.9 -m jupyterlab

## Install

```python
import pandas as pd
df = pd.read_csv("data.csv")

```

## Affichage

```python
df.head() # affiche 5 premieres lignes
df["champ1"].head() # affiche 5 premières lignes d'un champ
df.champ1.head() # affiche 5 premières lignes d'un champ
df.tail() # affiche 5 dernières lignes
df.head(10) # affiche 10 premières lignes
df.shape # affiche nb lignes et nb colonnes
df.columns.tolist() # affiche les champs
type(df) # pandas.core.frame.DataFrame
type(df.email) # pandas.core.series.Series
df.loc[10:20]  # affiche de la ligne 10 à 20 icnluses
df_email.loc[["bwymanb@lulu.com", "omaryone@va.gov"]]
```

## Index

```python
df.index #affiche start, stop et step de l'index
df.set_index("email", inplace=True ) # modifie l'index
df_email = df.set_index("email") # autre syntaxe de modification
```

## Filtres

```python
df["gender"] == "Male" # affiche True ou False
df[df.gender == "Male"] # filtre le df
df[df.country.isin(["France", "Canada"])]

```

## Manip données

```python
df_test = df.copy() # on copie le df
df_test[df_test.price_paid.apply(lambda x: x.replace("$", "")).astype(float) >= 5] # on filtre si price_paid > 5, en enlevant $
```

## Suppressions

```python
df.drop("ip_address", axis=1, inplace=True) # Supprime la colonne (Axe 1)

df.set_index("gender", inplace=True) # On commence par attribuer l'index
df.drop("Male", axis=0, inplace=True) # On supprime les lignes (Axe 0) selon valeur de l'index
```

## Valeurs

```python
df.isnull() # affiche les lignes avec au moins une valeur NaN
df.notnull() # inverse
df[df["Champ1"].notnull()].head() # 5 premières lignes donc Champs1 est pas NaN
df.tax.fillna(method='bfill') # Remplit les NaN par des valeurs autour
df.dropna(subset=["Champ1"], inplace=True) # Supprime les lignes dont Champ1 est NaN
```
