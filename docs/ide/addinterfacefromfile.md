---
title: "AddInterfaceFromFile | Microsoft Docs"
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
  - "AddInterfaceFromFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddInterfaceFromFile 메서드"
ms.assetid: fa848690-ad98-4fb4-bbcf-dffcaad05df2
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AddInterfaceFromFile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

인터페이스가 포함된 템플릿 파일을 렌더링하고 삽입합니다.  
  
## 구문  
  
```  
  
      function AddInterfaceFromFile(   
   oCM,   
   strInterfaceFile    
);  
```  
  
#### 매개 변수  
 `oCM`  
 [Visual C\+\+ Code Model](http://msdn.microsoft.com/ko-kr/dd6452c2-1054-44a1-b0eb-639a94a1216b) 개체  
  
 *strInterfaceFile*  
 경로를 제외한 템플릿 파일 이름입니다.  
  
## 설명  
 인터페이스가 포함된 템플릿 파일을 렌더링하고 프로젝트의 .idl 파일에 삽입하려면 이 함수를 호출합니다.  
  
 인터페이스를 추가하지 못하면 이 함수는 오류 메시지를 표시합니다.  
  
## 예제  
  
```  
// Render myint.idl and insert into strProject.idl  
AddInterfaceFromFile(oCM, "myint.idl");  
```  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ 마법사에서 사용하는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)