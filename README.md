<body>
<!-- partial:index.partial.html -->
  <div class="content">
    <h2>JumHc.PL</h2>
    <p>JumHc.pl jest najlepszym serverem w polsce </p>
  <!--partial -->

# Twój GitHub token
token = 'ghp_XXXXXXXXXXXXXXXXXXXXXXXXXXXX'

# Ustawienia nagłówków z autoryzacją
headers = {
    'Authorization': f'token {token}',
    'Accept': 'application/vnd.github.v3+json'
}

# Przykład: pobierz dane o swoim koncie
response = requests.get('https://api.github.com/user', headers=headers)

if response.status_code == 200:
    data = response.json()
    print("Zalogowano jako:", data['login'])
else:
    print("Błąd logowania:", response.status_code)

</body>
