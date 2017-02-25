---
title: "이름 대신 서수를 사용하여 DLL에서 함수 내보내기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "NONAME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL 내보내기[C++], 서수 값"
  - "함수 내보내기[C++], 서수 값"
  - "NONAME 특성"
  - "서수 내보내기[C++]"
ms.assetid: 679719fd-d965-4df3-9f7a-7d86ad831702
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 이름 대신 서수를 사용하여 DLL에서 함수 내보내기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DLL에서 함수를 내보내는 가장 간단한 방법은 이름을 사용하여 함수를 내보내는 것입니다.  예를 들어, **\_\_declspec\(dllexport\)**을 사용할 때 이 방법이 사용됩니다.  그러나 이름 대신 서수를 사용하여 함수를 내보낼 수도 있습니다.  이 방법을 사용할 경우에는 **\_\_declspec\(dllexport\)** 대신 .def 파일을 사용해야 합니다.  함수의 서수 값을 지정하려면 .def 파일에서 함수 이름에 서수를 추가합니다.  서수 지정에 대한 자세한 내용은 [.def 파일을 사용하여 DLL에서 내보내기](../build/exporting-from-a-dll-using-def-files.md)를 참조하십시오.  
  
> [!TIP]
>  DLL의 파일 크기를 최적화하려면 내보내는 각 함수에 **NONAME** 특성을 사용합니다.  **NONAME** 특성을 사용하면 DLL의 내보내기 테이블에 함수 이름 대신 서수가 저장됩니다.  따라서 많은 함수를 내보내는 경우에 파일 크기를 상당히 줄일 수 있습니다.  
  
## 수행할 작업  
  
-   [.def 파일을 사용하여 서수로 내보내기](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [\_\_declspec\(dllexport\) 사용](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
## 참고 항목  
 [DLL에서 내보내기](../build/exporting-from-a-dll.md)