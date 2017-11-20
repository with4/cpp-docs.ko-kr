---
title: "const 및 volatile 포인터 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- volatile keyword [C++], and pointers
- pointers, and const
- pointers, and volatile
- const keyword [C++], volatile pointers
ms.assetid: 0c92dc6c-400e-4342-b345-63ddfe649d7e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ebf8d12c7c3b0f9578724fe772f24c0bc8c845ac
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="const-and-volatile-pointers"></a>const 및 volatile 포인터
[const](../cpp/const-cpp.md) 및 [휘발성](../cpp/volatile-cpp.md) 키워드는 포인터 처리 방법을 변경 합니다. **const** 키워드 지정 초기화 된 후 포인터를 수정할 수 없습니다 5d; 포인터 이후에 수정 되지 않도록에서 보호 됩니다.  
  
 `volatile` 키워드는 그 뒤에 오는 이름과 관련된 값을 사용자 응용 프로그램을 사용하지 않고도 변경할 수 있도록 지정합니다. 따라서, `volatile` 키워드는 중단 서비스 루틴과의 통신에 사용되는 다중 처리나 전역 데이터 영역에서 접근할 수 있는 공유 메모리에서 개체를 선언하는 데 유용합니다.  
  
 이름을 `volatile`로 선언한 경우, 컴파일러가 프로그램에 액세스할 때마다 메모리에서 값을 다시 로딩하기 때문에 개체의 최적화 횟수가 상당히 줄어들게 됩니다. 이 키워드는 개체 상태가 예기치 않게 변경되는 경우 예상 가능한 프로그램 성능을 보장하는 유일한 방법이기도 합니다.  
  
 으로 포인터에서 가리키는 개체를 선언 하려면 **const** 또는 `volatile`, 선언 형식 사용 하 여:  
  
```  
const char *cpch;  
volatile char *vpch;  
```  
  
 포인터의 값을 선언 하려면-포인터에 저장 된 실제 주소 즉,-으로 **const** 또는 `volatile`, 선언 형식 사용 하 여:  
  
```  
char * const pchc;  
char * volatile pchv;  
```  
  
 개체의 수정을 허용 하는 할당을 방지 하는 c + + 언어 또는 포인터가 선언으로 **const**합니다. 그와 같은 할당은 개체 또는 포인터가 선언된 정보를 제거하기 때문에 원래의 선언 의도에 위배됩니다. 다음의 선언을 살펴보세요.  
  
```  
const char cch = 'A';  
char ch = 'B';  
```  
  
 주어진 두 개체의 이전 선언 (`cch`, 형식의 **const char**, 및 `ch`, 형식의 **char)**, 다음과 같은 선언/초기화는 사용할 수:  
  
```  
const char *pch1 = &cch;  
const char *const pch4 = &cch;  
const char *pch5 = &ch;  
char *pch6 = &ch;  
char *const pch7 = &ch;  
const char *const pch8 = &ch;  
```  
  
 다음의 선언/초기화는 잘못되었습니다.  
  
```  
char *pch2 = &cch;   // Error  
char *const pch3 = &cch;   // Error  
```  
  
 `pch2` 선언은 상수 개체가 수정될 수 있는 포인터를 선언하기 때문에 허용되지 않습니다. `pch3` 선언은 `pointer`가 개체가 아닌 상수임을 지정하기 때문에 `pch2` 선언과 마찬가지 이유로 허용되지 않습니다.  
  
 다음 8개의 할당에서는 포인터를 통한 할당과 이전 선언에 대한 포인터 값의 변경을 표시합니다. 이제 `pch1`을 통해 `pch8`에 대한 초기화가 올바르다고 가정합니다.  
  
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
  
 로 선언 된 포인터 `volatile`, 또는의 혼합으로 **const** 및 `volatile`, 동일한 규칙을 따릅니다.  
  
 에 대 한 포인터 **const** 개체 종종 함수 선언에 다음과 같이 사용 됩니다.  
  
```  
errno_t strcpy_s( char *strDestination, size_t numberOfElements, const char *strSource );  
```  
  
 위의 문은 함수를 선언 [strcpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)형식의 포인터가 있는 세 개의 인수 중 두 개, `char`합니다. 참조로 인수 전달 하 고 하지 값별로 함수는 모두 수정할 수 있으므로 `strDestination` 및 `strSource` 경우 `strSource` 로 선언 되지 않은 **const**합니다. 선언 `strSource` 으로 **const** 호출자에 게를 보장 `strSource` 호출된 된 함수에서 변경할 수 없습니다.  
  
> [!NOTE]
>  표준 변환 되기 때문에 *typename*  **\***  를 **const** *typename*  **\*** 는 형식의 인수를 전달할 수 **char \***  를 [strcpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)합니다. 그러나 하지도 마찬가지입니다. 제거 하는 암시적 변환이 존재는 **const** 개체 또는 포인터에서 특성입니다.  
  
 A **const** 지정 된 형식의 포인터는 동일한 형식의 포인터에 할당할 수 있습니다. 그러나 한가 아닌 포인터 **const** 에 할당할 수 없습니다는 **const** 포인터입니다. 다음 코드는 올바른 할당과 잘못된 할당을 보여 줍니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [포인터](../cpp/pointers-cpp.md)