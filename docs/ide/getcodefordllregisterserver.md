---
title: "GetCodeForDllRegisterServer | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetCodeForDllRegisterServer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetCodeForDllRegisterServer 메서드"
ms.assetid: 2fe733ad-3f1e-4020-9ce3-68956da7d41d
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# GetCodeForDllRegisterServer
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

서버를 등록 하는 적절 한 코드를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      function GetCodeForDllRegisterServer(   
   nLineStart,   
   nLineEnd    
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `nLineStart`  
 함수 시작 부분에 대 한 0부터 시작 줄 번호입니다.  
  
 `nLineEnd`  
 함수의 끝에 대 한 0부터 시작 줄 번호입니다.  
  
## <a name="return-value"></a>반환 값  
 서버를 등록 하기 위한 코드를 포함 하는 문자열  
  
## <a name="remarks"></a>설명  
 서버를 등록 하는 것에 대 한 적절 한 코드를 검색 하려면이 멤버 함수를 호출 합니다.  
  
|줄 번호|코드|  
|-----------------|----------|  
|0|AFX_MANAGE_STATE(AfxGetStaticModuleState());|  
|1|_AtlModule.UpdateRegistryAppId(TRUE);|  
|2|HRESULT hRes = _AtlModule.RegisterServer(TRUE);|  
|3|경우 (hRes! S_OK =)|  
|4|\treturn hRes;|  
|5|if (!입니다. COleObjectFactory::UpdateRegistryAll(TRUE))|  
|6|\treturn ResultFromScode(SELFREG_E_CLASS);|  
|7|S_OK를 반환 합니다.|  
  
 반환 되는 줄은 각각에 대 한 `GetCodeForDllRegisterServer` 선행 탭 추가 (`\t`) 및 후행 "CR-LF" (캐리지 리턴-줄 바꿈) 문자 쌍 (`\r\n`).  
  
## <a name="example"></a>예제  
  
```  
// Get the lines numbered 2 and 3 above  
GetCodeForDllRegisterServer(2, 3)  
  
// returns the following string  
// "\tHRESULT hRes = _AtlModule.RegisterServer(TRUE);\r\n\tif (hRes != S_OK)\r\n"  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [공용 JScript 함수를 사용 하 여 c + + 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C + + 마법사는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)   
 [GetCodeForDllUnregisterServer](../ide/getcodefordllunregisterserver.md)