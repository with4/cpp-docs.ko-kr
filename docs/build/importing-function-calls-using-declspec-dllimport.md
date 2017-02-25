---
title: "__declspec(dllimport)을 사용하여 함수 호출 가져오기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__declspec"
  - "dllimport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec(dllimport) 키워드[C++]"
  - "dllimport 특성[C++], 함수 호출 가져오기"
  - "함수 호출[C++], 가져오기"
  - "함수 호출 가져오기[C++]"
ms.assetid: 6b53c616-0c6d-419a-8e2a-d2fff20510b3
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# __declspec(dllimport)을 사용하여 함수 호출 가져오기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음의 코드 예제는 **\_declspec\(dllimport\)**을 사용하여 DLL에서 응용 프로그램으로 함수 호출을 가져오는 방법을 보여 줍니다.  이 예제에서는 `func1`이 **main** 함수가 들어 있는 .exe 파일과는 별도로 DLL에 상주하는 함수라고 가정합니다.  
  
 **\_\_declspec\(dllimport\)**을 사용하지 않은 경우의 코드는 다음과 같습니다.  
  
```  
int main(void)   
{  
   func1();  
}  
```  
  
 컴파일러는 다음과 같은 코드를 생성합니다.  
  
```  
call func1  
```  
  
 그러면 링커에서 이 호출을 다음과 같은 형식으로 변환합니다.  
  
```  
call 0x4000000         ; The address of 'func1'.  
```  
  
 `func1`이 다른 DLL에 있는 경우 링커는 `func1`의 주소를 알 수 없기 때문에 이 함수를 직접 확인할 수 없습니다.  16비트 환경에서 링커는 로더가 런타임에 올바른 주소를 사용하여 패치하게 되는 .exe 파일의 목록에 이 코드 주소를 추가합니다.  32비트 및 64비트 환경에서는 링커가 해당 주소를 알고 있는 썽크를 생성합니다.  32비트 환경에서는 썽크가 다음과 같습니다.  
  
```  
0x40000000:    jmp DWORD PTR __imp_func1  
```  
  
 여기서 `imp_func1`은 .exe 파일의 가져오기 주소 테이블에 있는 `func1`의 슬롯 주소입니다.  따라서 링커에서는 모든 주소를 알 수 있습니다.  로더는 로드 시 모든 함수가 올바르게 작동할 수 있도록 .exe 파일의 가져오기 주소 테이블을 업데이트하기만 하면 됩니다.  
  
 링커는 필요하지 않으면 썽크를 생성하지 않으므로 **\_\_declspec\(dllimport\)**을 사용하는 것이 더 좋습니다.  썽크는 코드의 길이를 늘리고\(RISC 시스템에서는 여러 개의 명령이 될 수 있음\) 캐시 성능을 저하시킬 수 있습니다.  사용자가 컴파일러에게 함수가 DLL에 있다고 알려주는 경우에는 컴파일러에서 자동으로 간접 호출을 생성할 수 있습니다.  
  
 예를 들어, 다음과 같은 코드가 있습니다.  
  
```  
__declspec(dllimport) void func1(void);  
int main(void)   
{  
   func1();  
}  
```  
  
 위의 코드는 다음과 같은 명령을 생성합니다.  
  
```  
call DWORD PTR __imp_func1  
```  
  
 여기에는 썽크와 `jmp` 명령이 없으므로 코드 길이가 줄어들고 속도도 빨라집니다.  
  
 반면, DLL 내부에 있는 함수 호출의 경우 간접 호출을 사용하지 않을 수도 있습니다.  사용자는 함수의 주소를 이미 알고 있으며,  간접 호출 전에 해당 함수의 주소를 로드하거나 저장하는 데에는 시간과 공간이 필요합니다. 따라서 항상 직접 호출이 더 빠르고 차지하는 공간도 더 작습니다.  DLL의 외부에서 DLL 함수를 호출할 때 **\_\_declspec\(dllimport\)**만 사용하려는 경우도 있습니다.  이 경우에는 DLL을 빌드할 때 해당 DLL 내부의 함수에 대해 **\_\_declspec\(dllimport\)**을 사용하지 않습니다.  
  
## 참고 항목  
 [응용 프로그램으로 가져오기](../build/importing-into-an-application.md)