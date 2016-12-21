---
title: "기반 포인터 (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__based"
  - "__based_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__based 키워드[C++]"
  - "기반 포인터"
  - "포인터, 기반"
ms.assetid: 1e5f2e96-c52e-4738-8e14-87278681205e
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 기반 포인터 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 `__based` 키워드를 통해 기존 포인터에서 오프셋된 포인터에 기반하여 포인터를 선언할 수 있습니다.  
  
## 구문  
  
```  
  
type __based( base ) declarator   
```  
  
## 설명  
 포인터 주소에 기반한 포인터는 32비트 또는 64비트 컴파일에서만 유효한 `__based` 키워드 형식입니다.  Microsoft 32비트 C\/C\+\+ 컴파일러의 기반 포인터는 32비트 포인터 기반에서 오프셋된 32비트입니다.  이 제한과 유사하게 64비트 환경에서 기반 포인터는 64비트 기반에서 오프셋된 64비트입니다.  
  
 포인터 기반의 포인터는 포인터가 포함된 영구 식별자에 사용됩니다.  포인터 기반의 포인터로 구성된 연결 목록은 디스크에 저장한 다음, 유효한 포인터를 이용하여 메모리의 다른 장소로 다시 로드할 수 있습니다.  예를 들면 다음과 같습니다.  
  
```  
// based_pointers1.cpp  
// compile with: /c  
void *vpBuffer;  
struct llist_t {  
   void __based( vpBuffer ) *vpData;  
   struct llist_t __based( vpBuffer ) *llNext;  
};  
```  
  
 `vpBuffer` 포인터는 나중에 프로그램에 할당된 메모리 주소로 할당됩니다.  연결 목록은 `vpBuffer` 값을 기준으로 재배치됩니다.  
  
> [!NOTE]
>  포인터가 포함된 영구 식별자는 [메모리 매핑된 파일](http://msdn.microsoft.com/library/windows/desktop/aa366556)을 사용하여 수행할 수도 있습니다  
  
 기반 포인터를 역참조하는 경우 기반은 반드시 명시적으로 지정하거나 선언을 통해 암시적으로 알려야 합니다.  
  
 이전 버전과의 호환성을 위해 **\_based**는 `__based`의 동의어입니다.  
  
## 예제  
 다음 코드는 기반 변경을 통한 기반 포인터 변경을 설명합니다.  
  
```  
// based_pointers2.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int a1[] = { 1,2,3 };  
int a2[] = { 10,11,12 };  
int *pBased;  
  
typedef int __based(pBased) * pBasedPtr;  
  
using namespace std;  
int main() {  
   pBased = &a1[0];  
   pBasedPtr pb = 0;  
  
   cout << *pb << endl;  
   cout << *(pb+1) << endl;  
  
   pBased = &a2[0];  
  
   cout << *pb << endl;  
   cout << *(pb+1) << endl;  
}  
```  
  
  **1**  
**2**  
**10**  
**11**   
## 참고 항목  
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [alloc\_text](../preprocessor/alloc-text.md)