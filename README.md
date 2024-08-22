import requests
import base64

# GitHub kişisel erişim token'ınızı buraya girin
token = "your_github_token"

# Kullanıcı adınız ve depo adınız
username = "your_github_username"
repo = "your_repo_name"

# Oluşturulacak dosyanın yolu ve adı
file_path = "example.txt"

# Dosyaya eklenecek içerik
content = "MERHABA SERAPİS, GitHub!"

# Base64 formatına dönüştürme
content_encoded = base64.b64encode(content.encode("utf-8")).decode("utf-8")

# GitHub API URL'si
url = "https://api.github.com/repos/{username}/{repo}/contents/{file_path}"

# API'ye gönderilecek veri
data = {
    "message": "Add example.txt",
    "content": content_encoded,
}

# API isteğini gerçekleştirme
response = requests.put(url, json=data, headers={
    "Authorization": f"token {token}",
    "Accept": "application/vnd.github.v3+json"
})

# Sonuç
if response.status_code == 201:
    print("Dosya başarıyla oluşturuldu!")
else:
    print("Dosya oluşturulamadı.")
    print(response.json())
