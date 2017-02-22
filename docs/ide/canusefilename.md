---
title: "CanUseFileName | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CanUseFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanUseFileName 메서드"
ms.assetid: 60b669fa-9484-4435-b502-78ec8e960a00
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CanUseFileName
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

파일이 있는지 확인합니다.  파일이 있으며 제한되어 있지 않으면 마법사에서 기존 파일에 추가할 코드를 병합하라는 메시지를 표시합니다.  
  
## 구문  
  
```  
  
      function CanUseFileName(   
   strFileName,   
   bCheckIfMidlHeader,   
   bCannotExist,   
   bSetMergeFlag    
);  
```  
  
#### 매개 변수  
 `strFileName`  
 확인할 파일 이름입니다.  
  
 *bCheckIfMidlHeader*  
 파일 이름이 MIDL에 의해 생성되었는지 검사하려면 **true**로 설정합니다.  
  
 *bCannotExist*  
 파일 이름이 이미 있고 덮어쓸 수 없는지 확인하려면 **true**로 설정합니다.  
  
 *bSetMergeFlag*  
 사용자가 기존 파일 이름에 코드를 병합할 수 있음을 나타내는 MERG\_FILE 기호를 포함시키려면 **true**로 설정합니다.  
  
## 반환 값  
 `strFileName`이 고유하거나 코드를 기존 파일에 추가할 수 있으면 **true**이고 그렇지 않으면 **false**입니다.  
  
## 설명  
 파일 이름이 있는지 검사하려면 이 함수를 호출합니다.  파일 이름이 있고 MIDL에 의해 생성되지 않았거나 제한되어 있지 않으면 이 함수는 기존 파일에 새 코드를 병합하라는 메시지를 표시합니다.  
  
 파일 이름이 없고 제한되어 있지 않으면 지정한 이름의 파일이 만들어집니다.  
  
 파일 이름을 MIDL에 의해 생성되었거나 제한되어 있으면 마법사에 오류 메시지가 표시됩니다.  
  
## 예제  
  
```  
case "HTML_FILE":  
if (!HTML_FILE.disabled)  
   {  
   if (!window.external.FindSymbol("HTML_FILE_VALID"))  
      {  
      bValid = CanUseFileName(obj.value, false, true);  
      if (!bValid)  
      break;  
      window.external.AddSymbol("HTML_FILE_VALID", true)  
      }  
   }  
   bValid = window.external.ValidateFile(HTML_FILE.value, vsCMValidateFileExtHtml);  
   break;   
```  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ 마법사에서 사용하는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)