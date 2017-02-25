---
title: "const 및 volatile 포인터 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const 키워드[C++], volatile 포인터"
  - "포인터, const"
  - "포인터, volatile"
  - "volatile 키워드[C++], 포인터"
ms.assetid: 0c92dc6c-400e-4342-b345-63ddfe649d7e
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# const 및 volatile 포인터
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[const](../cpp/const-cpp.md) 및 [volatile](../cpp/volatile-cpp.md) 키워드는 포인터 처리 방법을 변경합니다.  **const** 키워드는 포인터가 초기화 후 수정될 수 없도록 지정하여 이후 포인터가 수정되지 않도록 보호합니다.  
  
 `volatile` 키워드는 그 뒤에 오는 이름과 관련된 값을 사용자 응용 프로그램을 사용하지 않고도 변경할 수 있도록 지정합니다.  따라서, `volatile` 키워드는 중단 서비스 루틴과의 통신에 사용되는 다중 처리나 전역 데이터 영역에서 접근할 수 있는 공유 메모리에서 개체를 선언하는 데 유용합니다.  
  
 이름을 `volatile`로 선언한 경우, 컴파일러가 프로그램에 액세스할 때마다 메모리에서 값을 다시 로딩하기 때문에  개체의 최적화 횟수가 상당히 줄어들게 됩니다.  이 키워드는 개체 상태가 예기치 않게 변경되는 경우 예상 가능한 프로그램 성능을 보장하는 유일한 방법이기도 합니다.  
  
 포인터가 가리키고 있는 개체를 **const** 또는 `volatile`로 선언하려면, 다음과 같은 선언 형식을 사용합니다.  
  
```  
const char *cpch;  
volatile char *vpch;  
```  
  
 포인터의 값, 즉 포인터에 저장된 실제 주소를 **const** 또는 `volatile`로 선언하려면, 다음과 같은 선언 형식을 사용합니다.  
  
```  
char * const pchc;  
char * volatile pchv;  
```  
  
 C\+\+ 언어에서는 **const**로 선언된 개체 또는 포인터의 수정을 허용하는 할당을 금지합니다.  그와 같은 할당은 개체 또는 포인터가 선언된 정보를 제거하기 때문에 원래의 선언 의도에 위배됩니다.  다음의 선언을 살펴보십시오.  
  
```  
const char cch = 'A';  
char ch = 'B';  
```  
  
 이전 두 개체의 선언\(**const char** 형식의 `cch` 및 **char** 형식의 `ch`\)이 주어진 경우, 다음의 선언\/초기화가 유효합니다.  
  
```  
const char *pch1 = &cch;  
const char *const pch4 = &cch;  
const char *pch5 = &ch;  
char *pch6 = &ch;  
char *const pch7 = &ch;  
const char *const pch8 = &ch;  
```  
  
 다음의 선언\/초기화는 잘못되었습니다.  
  
```  
char *pch2 = &cch;   // Error  
char *const pch3 = &cch;   // Error  
```  
  
 `pch2` 선언은 상수 개체가 수정될 수 있는 포인터를 선언하기 때문에 허용되지 않습니다.  `pch3` 선언은 `pointer`가 개체가 아닌 상수임을 지정하기 때문에 `pch2` 선언과 마찬가지 이유로 허용되지 않습니다.  
  
 다음 8개의 할당에서는 포인터를 통한 할당과 이전 선언에 대한 포인터 값의 변경을 표시합니다. 이제 `pch8`을 통해 `pch1`에 대한 초기화가 올바르다고 가정합니다.  
  
```  
*pch1 = 'A';  // Error: object declared const  
pch1 = &ch;   // OK: pointer not declared const  
*pch2 = 'A';  // OK: normal pointer  
pch2 = &ch;   // OK: normal pointer  
*pch3 = 'A';  // OK: object not declared const  
pch3 = &ch;   // Error: pointer declared const  
*pch4 = 'A';  // Error: object declared const  
pch4 = &ch;   // Error: pointer declared const  
```  
  
 `volatile`로 선언된 포인터 또는 **const**와 `volatile`의 혼합으로 선언된 포인터는 동일한 규칙을 따릅니다.  
  
 **const** 개체에 대한 포인터는 다음과 같은 함수 선언에 자주 사용됩니다.  
  
```  
errno_t strcpy_s( char *strDestination, size_t numberOfElements, const char *strSource );  
```  
  
 앞의 문에서 [strcpy\_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) 함수를 선언하면, 이 함수의 세 개 인수 중 두 개는 `char` 형식의 포인터가 됩니다.  인수는 값이 아닌 참조에 의해 전달되므로 `strSource`가 **const**로 선언되지 않은 경우, 함수는 `strDestination` 및 `strSource`를 모두 자유롭게 수정할 수 있습니다.  `strSource`를 **const**로 선언하면 호출된 함수가 `strSource`를 변경할 수 없음을 호출자에게 보장합니다.  
  
> [!NOTE]
>  **\*** 형식 이름이 **\* const** 형식 이름으로 표준 변환되기 때문에 **char \*** 형식의 인수를 [strcpy\_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)로 전달할 수 있습니다.  그러나 반대의 경우는 성립되지 않습니다. 개체 또는 포인터에서 **const** 특성을 제거하는 암시적 변환이 존재하지 않기 때문입니다.  
  
 주어진 형식의 **const** 포인터는 동일한 형식의 포인터에 할당할 수 있습니다.  하지만 **const**가 아닌 포인터는 **const** 포인터에 할당할 수 없습니다.  다음 코드는 올바른 할당과 잘못된 할당을 보여 줍니다.  
  
```  
// const_pointer.cpp  
int *const cpObject = 0;  
int *pObject;  
  
int main() {  
pObject = cpObject;  
cpObject = pObject;   // C3892  
}  
```  
  
 다음 샘플에서는 개체에 포인터에 대한 포인터가 있는 경우 개체를 const로 선언하는 방법을 보여 줍니다.  
  
```  
// const_pointer2.cpp  
struct X {  
   X(int i) : m_i(i) { }  
   int m_i;  
};  
  
int main() {  
   // correct  
   const X cx(10);  
   const X * pcx = &cx;  
   const X ** ppcx = &pcx;  
  
   // also correct  
   X const cx2(20);  
   X const * pcx2 = &cx2;  
   X const ** ppcx2 = &pcx2;  
}  
```  
  
## 참고 항목  
 [포인터](../cpp/pointers-cpp.md)