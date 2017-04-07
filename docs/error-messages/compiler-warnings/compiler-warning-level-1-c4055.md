---
---
# <a name="compiler-warning-level-1-c4055"></a>컴파일러 경고(수준 1) C4055  
  
'conversion': 'type1' 데이터 포인터에서 'type2' 함수 포인터로 캐스팅되었습니다.  
  
**사용 되지 않는:** Visual Studio 2017 및 이후 버전에서이 경고가 생성 되지 않습니다.

 데이터 포인터가 함수 포인터로 잘못 캐스팅된 것 같습니다. /Za가 지정된 경우에는 수준 1이고 /Ze가 지정된 경우에는 수준 4입니다.  
  
 다음 샘플에서는 C4055를 생성합니다.  
  
```C  
// C4055.c  
// compile with: /Za /W1 /c  
typedef int (*PFUNC)();  
int *pi;  
PFUNC f() {  
   return (PFUNC)pi;   // C4055  
}  
```  
  
 /Ze가 지정된 경우에는 이 경고가 수준 4입니다.  
  
```C  
// C4055b.c  
// compile with: /W4 /c  
typedef int (*PFUNC)();  
int *pi;  
PFUNC f() {  
return (PFUNC)pi;   // C4055  
}  
```