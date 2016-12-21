---
title: "HTML 파일 | Microsoft Docs"
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
  - "사용자 지정 마법사, HTML 파일"
  - "사용자 지정 마법사, 사용자 인터페이스"
  - "파일[C++], 사용자 지정 마법사로 만들기"
  - "HTML 페이지, 사용자 지정 마법사의 사용자 인터페이스"
  - "마법사의 사용자 인터페이스"
  - "마법사[C++], 사용자 지정 마법사의 사용자 인터페이스"
ms.assetid: 3b6ed080-6560-418b-b908-d84d71bdf145
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HTML 파일
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

마법사에 HTML 인터페이스인 사용자 인터페이스를 포함할 수 있습니다.  Default.htm 파일과 함께 여러 개의 .htm 파일을 마법사에 포함할 수 있습니다. 포함되는 .htm 파일의 수는 [사용자 지정 마법사](../ide/custom-wizard.md)의 **페이지 수** 상자에서 지정할 수 있습니다.  각 .htm 파일은 마법사의 HTML 페이지를 나타내고, HTML 페이지는 `Next` 및 **뒤로** 단추, 탭 또는 마법사를 디자인할 때 지정하는 다른 형식으로 액세스할 수 있습니다.  
  
 HTML 페이지에는 다음과 같은 항목이 포함됩니다.  
  
-   사용자 지정 옵션의 기본값을 나타내는 SYMBOL 태그.  사용자가 **마침**을 클릭하면 다음과 같이 기호가 기호 테이블에 쓰여집니다.  
  
```  
<SYMBOL NAME='HEADER_FILE' VALUE='MyHeader.h' TYPE=text></SYMBOL>  
```  
  
 기호 테이블에서 "HEADER\_FILE"로 식별되는 마법사 UI의 텍스트 상자에는 기본 텍스트 "MyHeader.h"가 포함됩니다.  마법사 UI에서 이 값을 변경할 수 있습니다. 그러면 **마침**을 클릭할 때 다음과 같이 프로젝트의 기호 테이블에 결과 값이 쓰여집니다.  
  
```  
<SYMBOL NAME='CHECKBOX1' TYPE=checkbox VALUE=false></SYMBOL>  
```  
  
 기호 테이블에 "CHECKBOX1"로 식별되는 마법사 UI의 텍스트 상자는 기본적으로 비어 있습니다.  HTML UI에서 이 상자를 선택할 수 있습니다. 그러면 **마침**을 클릭할 때 결과 값이 기호 테이블에 쓰여집니다.  
  
 각 .htm 파일은 사용자의 선택을 기호 테이블에 기록합니다.  
  
-   일반적으로 사용되는 유용한 JScript 함수가 포함된 [Common.js](../ide/customizing-cpp-wizards-with-common-jscript-functions.md) 및 Default.js의 포함 경로  
  
-   HTML에 표시할 프로젝트 이미지에 대한 참조  
  
-   마법사의 사용자 인터페이스 모양을 사용자 지정하는 HTML 텍스트와 서식  
  
-   마법사의 동작을 사용자 지정하기 위해 Visual C\+\+ 마법사 개체 모델에 액세스하는 JScript 함수.  이 함수는 다음 예제에 표시된 것처럼 HTML 페이지의 \<SCRIPT LANGUAGE\='JSCRIPT'\> 섹션에 있습니다.  
  
    > [!NOTE]
    >  HTML에서 마법사 및 환경 개체 모델에 액세스하려면 개체 모델 항목 앞에 "window.external"을 추가하십시오.  
  
    ```  
    function InitDocument(document)  
    {  
       setDirection();  
  
       if (window.external.FindSymbol('DOCUMENT_FIRST_LOAD'))  
       {  
          // This function sets the default symbols based   
          // on the values specified in the SYMBOL tags above  
          //  
          window.external.SetDefaults(document);  
       }  
  
       // Load the document and initialize the controls   
       // with the appropriate symbol values  
       //  
       window.external.Load(document);  
    }  
    ```  
  
 다음은 콘솔 응용 프로그램 마법사 샘플입니다.  
  
```  
<SYMBOL NAME='WIZARD_DIALOG_TITLE' TYPE=text VALUE='Console Application Wizard'></SYMBOL>  
  
<SYMBOL NAME='EMPTY_PROJECT' TYPE=checkbox VALUE=false></SYMBOL>  
<SYMBOL NAME='SUPPORT_ATL' TYPE=checkbox VALUE=false></SYMBOL>  
<SYMBOL NAME='SUPPORT_MFC' TYPE=checkbox VALUE=false></SYMBOL>  
```  
  
## 참고 항목  
 [마법사용으로 만들어진 파일](../ide/files-created-for-your-wizard.md)   
 [사용자 지정 마법사](../ide/custom-wizard.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)