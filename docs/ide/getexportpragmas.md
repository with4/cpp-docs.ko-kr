---
title: "GetExportPragmas | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetExportPragmas"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetExportPragmas 메서드"
ms.assetid: ef21f6a3-d83f-4e19-9323-ca28cc40c8fd
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# GetExportPragmas
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

내보내기 함수에 사용할 pragma를 추가합니다.  
  
## 구문  
  
```  
  
function GetExportPragmas( );  
  
```  
  
## 반환 값  
 내보내기 pragma가 포함된 문자열입니다.  다음 중 하나일 수 있습니다.  
  
-   `#pragma comment(linker, "/EXPORT:DllCanUnloadNow=_DllCanUnloadNow@0,PRIVATE")'`  
  
-   `#pragma comment(linker, "/EXPORT:DllGetClassObject=_DllGetClassObject@12,PRIVATE")`  
  
-   `#pragma comment(linker, "/EXPORT:DllRegisterServer=_DllRegisterServer@0,PRIVATE")`  
  
-   `#pragma comment(linker, "/EXPORT:DllUnregisterServer=_DllUnregisterServer@0,PRIVATE")`  
  
## 설명  
 내보내기 함수에 사용할 pragma를 추가하려면 이 함수를 호출합니다.  
  
## 예제  
  
```  
oDllCanUnloadNow.StartPoint.Insert(GetExportPragmas() + "\r\n");  
oCM.Synchronize();  
```  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ 마법사에서 사용하는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)   
 [주석](../preprocessor/comment-c-cpp.md)