## Video Notes

![vlcsnap-2022-07-09-09h03m53s616](https://user-images.githubusercontent.com/37560890/178090550-689472f4-b1ef-4399-baa6-9f131c2ac120.png)
![vlcsnap-2022-07-09-09h04m30s455](https://user-images.githubusercontent.com/37560890/178090552-21a9e591-9edd-4fde-965d-77273a6d8b5d.png)
![vlcsnap-2022-07-09-09h05m19s670](https://user-images.githubusercontent.com/37560890/178090554-7f2fcd6b-068b-482b-87bf-fe4616bd29ee.png)
![vlcsnap-2022-07-09-09h05m59s230](https://user-images.githubusercontent.com/37560890/178090555-1a6e6671-66ac-4148-bf00-6c84b45e31d0.png)
![vlcsnap-2022-07-09-09h06m13s189](https://user-images.githubusercontent.com/37560890/178090556-871d0bd0-3c16-4f2a-a7ce-aa11678e2041.png)
![vlcsnap-2022-07-09-09h13m43s670](https://user-images.githubusercontent.com/37560890/178090557-b061d102-46cb-467e-983c-8f5b9cb52081.png)
![vlcsnap-2022-07-09-09h13m54s806](https://user-images.githubusercontent.com/37560890/178090558-2be05bb4-ccd0-4fa2-ba0e-2af8de184497.png)
![vlcsnap-2022-07-09-09h14m19s225](https://user-images.githubusercontent.com/37560890/178090559-e85e1cb8-9094-4a45-a57d-6d750df5272a.png)
![vlcsnap-2022-07-09-09h15m06s695](https://user-images.githubusercontent.com/37560890/178090561-4cb97964-c22a-4215-af57-d2ae53bc784f.png)
![vlcsnap-2022-07-09-09h15m32s726](https://user-images.githubusercontent.com/37560890/178090566-d07d2de8-a1e4-4edb-9131-935f8ddb84e9.png)
![vlcsnap-2022-07-09-09h16m51s756](https://user-images.githubusercontent.com/37560890/178090576-813344a6-a2da-4932-a9ad-45e7fed44c97.png)
![vlcsnap-2022-07-09-09h17m25s544](https://user-images.githubusercontent.com/37560890/178090578-532a255f-6854-41c0-ab1c-8c77d60f8407.png)
![vlcsnap-2022-07-09-09h20m25s715](https://user-images.githubusercontent.com/37560890/178090580-21e59ae3-bc77-4249-af2d-d90e641b5358.png)
![vlcsnap-2022-07-09-09h20m38s354](https://user-images.githubusercontent.com/37560890/178090581-18b015ed-ec33-472c-8559-eaaf0e2fe98b.png)
![vlcsnap-2022-07-09-09h21m03s556](https://user-images.githubusercontent.com/37560890/178090584-4ba5460f-ab70-49f8-b388-7b5e88fdbcdd.png)
![vlcsnap-2022-07-09-09h21m33s366](https://user-images.githubusercontent.com/37560890/178090593-fea156cc-0076-4afd-9217-3125437bc304.png)
![vlcsnap-2022-07-09-09h21m46s762](https://user-images.githubusercontent.com/37560890/178090595-b3b32850-f09e-43fc-af90-684075d5cb6b.png)
![vlcsnap-2022-07-09-09h21m55s845](https://user-images.githubusercontent.com/37560890/178090596-faf7f772-3c49-4ddf-8e6e-a4174f73334d.png)
![vlcsnap-2022-07-09-09h22m16s473](https://user-images.githubusercontent.com/37560890/178090597-eda33036-3fbf-4666-858c-46b171296dfb.png)
![vlcsnap-2022-07-09-09h22m22s753](https://user-images.githubusercontent.com/37560890/178090599-9e9f5a1d-9583-40c8-9743-e13318d2f738.png)
![vlcsnap-2022-07-09-09h22m43s289](https://user-images.githubusercontent.com/37560890/178090603-c3ffa3a2-a377-4571-826e-f876a03a50db.png)
![vlcsnap-2022-07-09-09h22m56s133](https://user-images.githubusercontent.com/37560890/178090604-15d33509-057c-45bb-b504-1e16e350eadd.png)
![vlcsnap-2022-07-09-09h23m09s612](https://user-images.githubusercontent.com/37560890/178090605-40b00fb4-cf89-409c-ad91-509ece49f7ef.png)
![vlcsnap-2022-07-09-09h23m57s011](https://user-images.githubusercontent.com/37560890/178090608-13b35117-5e42-4860-8121-a5d12ac71351.png)
![vlcsnap-2022-07-09-09h24m30s720](https://user-images.githubusercontent.com/37560890/178090609-40cf401b-04c4-4eb7-b9fa-4c5720a82016.png)

```cpp
#include <iostream>
using namespace std;

// Initial counter
int count=0;

// Function calling
void f()
{
    if(count==4) return ;
    cout<<count<<endl;;
    count++;
    f();
}

// Main function
int main()
{
    // Calling the function
    f();

    return 0;
}

```
