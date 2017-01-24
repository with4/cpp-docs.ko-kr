---
title: "마법사 HTML 파일의 오류 처리 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "오류 처리, 파일 오류 검사"
  - "HTML, 오류 처리"
ms.assetid: eb428a64-b681-4420-987d-92098bf98455
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 마법사 HTML 파일의 오류 처리
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

사용자 인터페이스가 있는 마법사를 만들면 프로젝트에 .htm 파일이 포함됩니다.  이 파일을 사용하면 프로젝트를 사용자 지정할 수 있습니다.  자세한 내용은 [HTML 파일](../ide/html-files.md)을 참조하십시오.  
  
 프로젝트에 오류 처리를 포함해야 합니다.  다음 코드는 오류 처리 예제 코드입니다.  
  
### HTML에서 오류를 처리하려면  
  
1.  필드 유효성을 검사할 때 오류 정보를 설정해야 하는 유효성 검사 메서드를 DLL에서 호출하는 경우, 매개 변수를 사용하지 않고 `ReportError`를 호출합니다.  
  
    ```  
    function ValidateInput()  
    {  
       if (!window.external.ValidateFile(HEADER_FILE.value))  
       {  
          ReportError();  
          HEADER_FILE.focus();  
          return false;  
       }  
    }  
    ```  
  
2.  필드 유효성을 검사할 때 HTML 스크립트만 사용하여 필드 유효성을 검사하는 경우, `SetErrorInfo`를 먼저 호출한 다음 매개 변수를 사용하지 않고 `ReportError`를 호출합니다.  
  
    ```  
    function OnWhatever()  
    {  
       if (!ValidateInput())  
          window.external.ReportErrror();  
       ....  
    }  
  
    function ValidateInput()  
    {  
       .....  
  
       if (HEADER_FILE.value == IMPL_FILE.value)  
       {  
          var L_ErrMsg_Text = "Header and implementation files cannot have the same name.";  
          SetErrorInfo(L_ErrMsg_Text);  
          bValid = false;  
       }  
       if (TYPE.value == "")  
       {  
          var L_ErrMsg4_Text = "Type cannot be blank.";  
          SetErrorInfo(L_ErrMsg4_Text);  
          bValid = false;  
       }  
       return bValid;  
    }  
    ```  
  
3.  매개 변수를 사용하여 `ReportError`를 호출합니다.  
  
    ```  
    function ValidateInput()  
    {  
       if (!IsListed(strType))  
       {  
          var L_Invalid2_Text = "The variable type should be one of the types listed.";  
          window.external.ReportError(L_Invalid2_Text);  
          VariableType.focus();  
          return false;  
       }  
    }  
    ```  
  
4.  **새 프로젝트** 또는 **새 항목 추가** 대화 상자로 돌아가야 하는 경우, 다음과 같이 **VS\_E\_WIZBACKBUTTONPRESS**를 반환합니다.  
  
    ```  
    try  
    {  
       oCM   = window.external.ProjectObject.CodeModel;  
    }  
    catch(e)  
    {  
       var L_NCBError_Text = "Cannot access the Class View information   
    file. Class View information will not be available.";  
       window.external.ReportError(L_NCBError_Text);  
       return VS_E_WIZARDBACKBUTTONPRESS;  
    ```  
  
## 참고 항목  
 [마법사용으로 만들어진 파일](../ide/files-created-for-your-wizard.md)   
 [마법사 사용자 지정](../ide/customizing-your-wizard.md)