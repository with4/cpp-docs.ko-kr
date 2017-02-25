---
title: "DEF 파일을 사용하여 가져오기 | Microsoft Docs"
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
  - ".def 파일[C++], 가져오기"
  - "def 파일[C++], 가져오기"
  - "dllimport 특성[C++], DEF 파일"
  - "DLL[C++], DEF 파일"
  - "importing DLL[C++], DEF 파일"
ms.assetid: aefdbf50-f603-488a-b0d7-ed737bae311d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# DEF 파일을 사용하여 가져오기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**\_\_declspec\(dllimport\)**을 .def 파일과 함께 사용하려는 경우에는 올바르지 않은 코드로 인해 문제가 생길 가능성을 줄이기 위해 다음과 같이 .def 파일에서 CONSTANT를 DATA로 바꿔야 합니다.  
  
```  
// project.def  
LIBRARY project  
EXPORTS  
   ulDataInDll   DATA  
```  
  
 다음 표에는 그 이유가 나와 있습니다.  
  
|키워드|가져오기 라이브러리의 내보내기|내보내기|  
|---------|----------------------|----------|  
|`CONSTANT`|`_imp_ulDataInDll_ulDataInDll`|`_ulDataInDll`|  
|`DATA`|`_imp_ulDataInDll`|`_ulDataInDll`|  
  
 **\_\_declspec\(dllimport\)**과 CONSTANT를 사용하면 명시적 링크를 사용할 수 있도록 만들어진 .lib DLL 가져오기 라이브러리의 `imp` 버전과 데코레이팅되지 않은 이름이 모두 나열됩니다.  반면, **\_\_declspec\(dllimport\)**과 DATA를 사용하면 `imp` 버전의 이름만 나열됩니다.  
  
 CONSTANT를 사용하는 경우에는 다음의 코드 구문 중 하나를 사용하여 `ulDataInDll`에 액세스할 수 있습니다.  
  
```  
__declspec(dllimport) ULONG ulDataInDll; /*prototype*/  
if (ulDataInDll == 0L)   /*sample code fragment*/  
```  
  
 또는  
  
```  
ULONG *ulDataInDll;      /*prototype*/  
if (*ulDataInDll == 0L)  /*sample code fragment*/  
```  
  
 그러나 .def 파일에서 DATA를 사용하는 경우에는 다음 정의를 사용하여 컴파일된 코드만이 `ulDataInDll` 변수에 액세스할 수 있습니다.  
  
```  
__declspec(dllimport) ULONG ulDataInDll;  
  
if (ulDataInDll == 0L)   /*sample code fragment*/  
```  
  
 CONSTANT를 사용하는 경우, 추가 수준의 간접 참조를 사용하지 않으면 변수 자체가 아니라 가져오기 주소 테이블에 있는 변수에 대한 포인터에 액세스할 수 있으므로 보다 위험합니다.  가져오기 주소 테이블은 현재 컴파일러 및 링커에서 읽기 전용으로 만들어지기 때문에, 이러한 유형의 문제는 종종 액세스 위반으로 표시됩니다.  
  
 현재 Visual C\+\+ 링커는 .def 파일의 CONSTANT가 이러한 경우를 나타내면 경고를 표시합니다.  CONSTANT를 사용하는 유일한 이유는 헤더 파일에서 프로토타입에 **\_\_declspec\(dllimport\)**을 나열하지 않으면 일부 개체 파일을 다시 컴파일할 수 없기 때문입니다.  
  
## 참고 항목  
 [응용 프로그램으로 가져오기](../build/importing-into-an-application.md)