---
title: "마법사 JScript 파일의 오류 처리 | Microsoft Docs"
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
  - "오류 처리, JScript"
  - "JScript, 오류 처리"
  - "마법사 JScript 오류 처리"
ms.assetid: 6df3ba46-7ab6-484c-ac45-b08f4b6a5900
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 마법사 JScript 파일의 오류 처리
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

마법사를 만들면 프로젝트에 Default.js 파일과 Common.js 파일이 포함됩니다.  이 파일을 사용하면 프로젝트를 사용자 지정할 수 있습니다.  자세한 내용은 [JScript 파일](../ide/jscript-file.md)을 참조하십시오.  
  
 프로젝트에 오류 처리를 포함해야 합니다.  다음 코드는 오류 처리 예제 코드입니다.  
  
### JScript에서 오류를 처리하려면  
  
1.  **마침**을 클릭할 때 오류를 확인하려면 다음 코드를 입력합니다.  
  
    ```  
    function OnFinish(selProj, Class)  
    {  
       try  
       {  
          .....  
       }  
       catch(e)  
       {  
          if (e.description.length != 0)  
             SetErrorInfo(e.description, e.number);  
          return e.number  
       }  
    }  
    ```  
  
2.  스크립트에서 호출되는 도우미 스크립트 함수에서 `e`를 throw합니다.  
  
    ```  
    function ExtenderFromType(strVariableType)  
    {  
       try  
       {  
          ....  
       }  
       catch(e)  
       {  
          throw e;  
       }  
    }  
    ```  
  
3.  [.vsz 파일](../ide/dot-vsz-file-project-control.md)에 **PREPROCESS\_FUNCTION** 매개 변수가 있으면 마법사에서 [CanAddATLClass](../ide/jscript-functions-for-cpp-wizards.md)를 호출합니다.  실패할 경우에는 [SetErrorInfo](../ide/seterrorinfo.md)를 사용하고 **false**를 반환합니다.  
  
    ```  
    function CanAddATLClass(oProj, oObject)  
    {  
       try  
       {  
          if (!IsATLProject(oProj))  
          {  
             if (!IsMFCProject(oProj, true))  
             {     
                var L_CanAddATLClass_Text = "ATL classes can only be added  
     to ATL, MFC EXE and MFC regular DLL projects.";  
                wizard.ReportError(L_CanAddATLClass_Text);  
                return false;  
             }  
             else  
             {  
                .....  
                var bRet = AddATLSupportToProject(oProj);  
                .....  
                return bRet;  
             }  
          }  
          return true;  
       }  
       catch(e)  
       {  
          throw e;  
       }  
    }  
    ```  
  
4.  **새 프로젝트** 또는 **새 항목 추가** 대화 상자로 돌아가야 하는 경우, 다음과 같이 **VS\_E\_WIZBACKBUTTONPRESS**를 반환합니다.  
  
    ```  
    function OnFinish(selProj, Class)  
    {  
       ....  
       if (!CheckAddtoProject(selProj))  
       {  
          return VS_E_WIZARDBACKBUTTONPRESS;  
       }  
    }  
    ```  
  
## 참고 항목  
 [마법사용으로 만들어진 파일](../ide/files-created-for-your-wizard.md)   
 [마법사 사용자 지정](../ide/customizing-your-wizard.md)