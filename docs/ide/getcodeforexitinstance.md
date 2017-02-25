---
title: "GetCodeForExitInstance | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetCodeForExitInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetCodeForExitInstance 메서드"
ms.assetid: 41fe3d79-a1f4-4bb5-b3f5-7859e255b4e7
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# GetCodeForExitInstance
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

가져옵니다는 [ExitInstance](../Topic/CWinApp::ExitInstance.md) 마법사를 종료 하는 것에 대 한 코드입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      function GetCodeForExitInstance(   
   nLineStart,   
   nLineEnd    
)   
```  
  
#### <a name="parameters"></a>매개 변수  
 `nLineStart`  
 함수 시작 부분에 대 한 0부터 시작 줄 번호입니다.  
  
 `nLineEnd`  
 함수의 끝에 대 한 0부터 시작 줄 번호입니다.  
  
## <a name="return-value"></a>반환 값  
 마법사 인스턴스를 종료 하는 것에 대 한 코드를 포함 하는 문자열입니다.  
  
## <a name="remarks"></a>설명  
 마법사의 인스턴스를 종료 하는 데 적절 한 코드를 검색 하려면이 멤버 함수를 호출 합니다.  
  
|줄 번호|ExitInstance 코드|  
|-----------------|-----------------------|  
|0|_AtlModule.RevokeClassObjects();|  
|1|CWinApp::ExitInstance();를 반환 합니다.|  
  
 반환 되는 줄은 각각에 대 한 `GetCodeForExitInstance` 선행 탭 추가 (`\t`) 및 후행 "CR-LF" (캐리지 리턴-줄 바꿈) 문자 쌍 (`\r\n`).  
  
## <a name="example"></a>예제  
  
```  
if (!oExitInstance)  
   {  
      oExitInstance = oCWinApp.AddFunction("ExitInstance",   
      vsCMFunctionFunction, "BOOL", vsCMAddPositionEnd, vsCMAccessPublic,   
      strProjectCPP);  
      oExitInstance.BodyText = GetCodeForExitInstance(0, 1);  
   }  
// returns the following string  
// "\t_AtlModule.RevokeClassObjects();\r\n  
// \treturn CWinApp::ExitInstance();\r\n"  
else  
   {  
   oExitInstance.StartPointOf(vsCMPartBody,   
   vsCMWhereDefinition).CreateEditPoint().Insert(GetCodeForExitInstance(0,   
   0));  
// returns the following string  
// "\t_AtlModule.RevokeClassObjects();\r\n  
      oCM.Synchronize();  
   }  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [공용 JScript 함수를 사용 하 여 c + + 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C + + 마법사는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)   
 [GetCodeForDllCanUnloadNow](../ide/getcodefordllcanunloadnow.md)   
 [GetCodeForInitInstance](../ide/getcodeforinitinstance.md)