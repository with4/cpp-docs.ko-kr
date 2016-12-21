---
title: "GetCodeForInitInstance | Microsoft Docs"
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
  - "GetCodeForInitInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetCodeForInitInstance 메서드"
ms.assetid: cfa4cb9f-d1cc-4be6-8db9-c253655b57e4
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# GetCodeForInitInstance
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정한 코드에서 [InitInstance](../Topic/CWinApp::InitInstance.md)를 검색합니다.  
  
## 구문  
  
```  
  
      function GetCodeForInitInstance(   
   nLineStart,   
   nLineEnd    
);  
```  
  
#### 매개 변수  
 `nLineStart`  
 함수를 시작할 때 사용되는 0에서 시작되는 줄 번호입니다.  
  
 `nLineEnd`  
 함수가 끝날 때 사용되는 0에서 시작되는 줄 번호입니다.  
  
## 반환 값  
 마법사 인스턴스를 초기화하는 데 사용하는 코드가 포함된 문자열입니다.  
  
## 설명  
 마법사 인스턴스를 초기화하는 데 사용하는 해당 코드를 검색하려면 이 멤버 함수를 호출합니다.  줄 번호는 다음과 같습니다.  
  
|줄 번호|InitInstance 코드|  
|----------|---------------------|  
|0|`CWinApp::InitInstance();`|  
|1|`return TRUE;`|  
|2|`AfxOleInit();`|  
|3|`// Parse command line for standard shell commands, DDE, file open`|  
|4|`CCommandLineInfo cmdInfo;`|  
|5|`ParseCommandLine(cmdInfo);`|  
|6|`// App was launched with /Embedding or /Automation switch.`|  
|7|`// Run app as automation server.`|  
|8|`if (cmdInfo.m_bRunEmbedded &#124;&#124; cmdInfo.m_bRunAutomated)`|  
|9|`{`|  
|10|`\t// Register class factories via CoRegisterClassObject().`|  
|11|`\tif (FAILED(_AtlModule.RegisterClassObjects(CLSCTX_LOCAL_SERVER, REGCLS_MULTIPLEUSE)))`|  
|12|`\t\treturn FALSE;`|  
|13|`\t// Don't show the main window`|  
|14|`\treturn TRUE;`|  
|15|`}`|  
|16|`// App was launched with /Unregserver or /Unregister switch.`|  
|17|`if (cmdInfo.m_nShellCommand == CCommandLineInfo::AppUnregister)`|  
|18|`{`|  
|19|`\t_AtlModule.UpdateRegistryAppId(FALSE);`|  
|20|`\t_AtlModule.UnregisterServer(TRUE);`|  
|21|`\treturn FALSE;`|  
|22|`}`|  
|23|`// App was launched with /Register or /Regserver switch.`|  
|24|`if (cmdInfo.m_nShellCommand == CCommandLineInfo::AppRegister)`|  
|25|`{`|  
|26|`\t_AtlModule.UpdateRegistryAppId(TRUE);`|  
|27|`\t_AtlModule.RegisterServer(TRUE);`|  
|28|`\treturn FALSE;`|  
|29|`}`|  
  
 `GetCodeForInitInstance`는 반환된 각 줄의 앞과 뒤에 각각 탭\(`\t`\)과 캐리지 리턴\-줄 바꿈\(CR\-LF\) 조합\(`\r\n`\)을 추가합니다.  
  
## 예제  
  
```  
// Get the lines numbered 0 through 2 above  
GetCodeForInitInstance(0, 2)  
  
// returns the following string  
// "\tCWinApp::InitInstance();\r\n\treturn TRUE;\r\n\tAfxOleInit();\r\n"  
  
```  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ 마법사에서 사용하는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)   
 [GetCodeForExitInstance](../ide/getcodeforexitinstance.md)