## Video Notes

![vlcsnap-2022-07-09-11h04m16s882](https://user-images.githubusercontent.com/37560890/178093722-73a1bfef-4105-46bd-873f-efb2c24ca214.png)
![vlcsnap-2022-07-09-11h08m33s125](https://user-images.githubusercontent.com/37560890/178093725-a9e943d9-661a-40a0-9f79-e5b56997984b.png)
![vlcsnap-2022-07-09-11h09m09s675](https://user-images.githubusercontent.com/37560890/178093726-089c4cdd-32d2-4694-85d2-945f2d8b6ebd.png)
![vlcsnap-2022-07-09-11h09m27s542](https://user-images.githubusercontent.com/37560890/178093728-57e9519a-c0e2-4d41-8ba5-3cc4ba1ba782.png)
![vlcsnap-2022-07-09-11h09m51s969](https://user-images.githubusercontent.com/37560890/178093729-d0bc9c24-632e-4594-b07d-f06346312a99.png)
![vlcsnap-2022-07-09-11h10m04s319](https://user-images.githubusercontent.com/37560890/178093730-3c810767-7dc9-43b2-b6fa-1b66bbab87d4.png)
![vlcsnap-2022-07-09-11h10m21s056](https://user-images.githubusercontent.com/37560890/178093731-757a541f-3f25-4678-bb48-935787045350.png)
![vlcsnap-2022-07-09-11h10m58s333](https://user-images.githubusercontent.com/37560890/178093733-6a84e24c-0422-4a1f-917f-5f4a1fa54de9.png)
![vlcsnap-2022-07-09-11h19m53s925](https://user-images.githubusercontent.com/37560890/178093735-dedf53a2-be54-4efc-91d7-c862a5cd2ea7.png)
![vlcsnap-2022-07-09-11h22m09s183](https://user-images.githubusercontent.com/37560890/178093736-b62622fb-2bc3-454c-ab93-5aa2a7ba1e57.png)
![vlcsnap-2022-07-09-11h22m14s085](https://user-images.githubusercontent.com/37560890/178093738-974fe3b0-83cd-40fe-a68f-b6cad959cc03.png)
![vlcsnap-2022-07-09-11h22m37s499](https://user-images.githubusercontent.com/37560890/178093739-cae1f00f-a8ca-4b09-8899-e2ac5c538f15.png)
![vlcsnap-2022-07-09-11h22m50s088](https://user-images.githubusercontent.com/37560890/178093740-32d8a608-dd40-4ed7-9dc5-024aed9a9411.png)
![vlcsnap-2022-07-09-11h23m11s128](https://user-images.githubusercontent.com/37560890/178093741-579e3e6e-1683-4f5d-8fe4-562fec77b936.png)
![vlcsnap-2022-07-09-11h23m23s873](https://user-images.githubusercontent.com/37560890/178093744-64709909-6fba-495a-bbb3-0eb676241ce0.png)
![vlcsnap-2022-07-09-11h23m32s660](https://user-images.githubusercontent.com/37560890/178093746-f20bf619-c36e-49fc-b31e-268c325abed1.png)
![vlcsnap-2022-07-09-11h24m27s269](https://user-images.githubusercontent.com/37560890/178093747-c06ec1f6-6146-4616-8788-f59ef52f87d2.png)
![vlcsnap-2022-07-09-11h25m06s159](https://user-images.githubusercontent.com/37560890/178093748-75932fd7-ecc7-4257-92f9-9fe2e1c1ba40.png)
![vlcsnap-2022-07-09-11h25m36s442](https://user-images.githubusercontent.com/37560890/178093749-3cf01d22-2555-4304-84b8-e891fff72923.png)
![vlcsnap-2022-07-09-11h26m25s254](https://user-images.githubusercontent.com/37560890/178093751-aa4b352f-dec6-49a7-9896-13239ccdbd43.png)
![vlcsnap-2022-07-09-11h26m55s718](https://user-images.githubusercontent.com/37560890/178093753-117421af-5921-4ea4-af1d-e0a5ffc663a0.png)
![vlcsnap-2022-07-09-11h27m25s309](https://user-images.githubusercontent.com/37560890/178093754-cd0dacad-c6ef-4b21-97b7-6b30f071d502.png)


```cpp
#include<vector>
#include <iostream>
using namespace std;


// Function for recursion calls
int fib(int n)
{
    if(n<=1) return n;
    int last= fib(n-1);
    int slast= fib(n-2);
    return last+slast;
}
int main()
{
   cout<<fib(1);
    
    return 0;
}

```
