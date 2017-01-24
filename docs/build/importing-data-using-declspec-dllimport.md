---
title: "__declspec(dllimport)을 사용하여 데이터 가져오기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "dllimport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec(dllimport) 키워드[C++]"
  - "dllimport 특성[C++], 데이터 가져오기"
  - "데이터 가져오기[C++]"
  - "importing DLL[C++], __declspec(dllimport)"
ms.assetid: 0ae70b39-87c7-4181-8be9-e786e0db60b0
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __declspec(dllimport)을 사용하여 데이터 가져오기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

데이터의 경우 **\_\_declspec\(dllimport\)**을 사용하면 간접 참조의 계층을 편리하게 제거할 수 있습니다.  그러나 DLL에서 데이터를 가져올 때에는 여전히 가져오기 주소 테이블을 검색해야 합니다.  **\_\_declspec\(dllimport\)**을 사용하기 전에는 DLL에서 내보낸 데이터에 액세스할 때 다음과 같은 추가 수준의 간접 참조를 수행했습니다.  
  
```  
// project.h  
#ifdef _DLL   // If accessing the data from inside the DLL  
   ULONG ulDataInDll;  
  
#else         // If accessing the data from outside the DLL  
   ULONG *ulDataInDll;  
#endif  
```  
  
 그런 다음 해당 .DEF 파일에 있는 데이터를 내보내게 됩니다.  
  
```  
// project.def  
LIBRARY project  
EXPORTS  
   ulDataInDll   CONSTANT  
```  
  
 그리고 다음과 같이 해당 DLL 외부에서 이 데이터에 액세스합니다.  
  
```  
if (*ulDataInDll == 0L)   
{  
   // Do stuff here  
}  
```  
  
 데이터를 **\_\_declspec\(dllimport\)**으로 표시하면 컴파일러에서 간접 참조 코드를 자동으로 생성합니다.  따라서 사용자는 위에서 설명한 단계를 수행할 필요가 없습니다.  이미 설명한 것처럼 DLL을 빌드할 때에는 데이터에 대해 **\_\_declspec\(dllimport\)** 선언을 사용하지 않습니다.  DLL 내의 함수는 가져오기 주소 테이블을 사용하여 데이터 개체에 액세스하지 않으므로 추가 수준의 간접 참조를 수행하지 않아도 됩니다.  
  
 DLL에서 데이터를 자동으로 내보내려면 다음과 같은 선언이 사용됩니다.  
  
```  
__declspec(dllexport) ULONG ulDataInDLL;  
```  
  
## 참고 항목  
 [응용 프로그램으로 가져오기](../build/importing-into-an-application.md)