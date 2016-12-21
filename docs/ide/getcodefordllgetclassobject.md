---
title: "GetCodeForDllGetClassObject | Microsoft Docs"
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
  - "GetCodeForDllGetClassObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetCodeForDllGetClassObject 메서드"
ms.assetid: 67b61b3b-9784-494f-ba01-17bffa9941ff
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# GetCodeForDllGetClassObject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DLL 클래스 개체에 대 한 코드를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      function GetCodeForDllGetClassObject(   
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
 클래스 개체를 가져오기 위한 코드를 포함 하는 문자열입니다.  
  
## <a name="remarks"></a>설명  
 클래스 개체에 대 한 코드를 검색 하려면이 멤버 함수를 호출 합니다. 이 함수를 호출 하면 배열 요소를 연결 하 여 단일 문자열을 만듭니다.  
  
 다음 표에서 클래스 개체에 대 한 코드를 가져오기 위한 코드를 보여 줍니다.  
  
|줄 번호|코드|  
|-----------------|----------|  
|0|AFX_MANAGE_STATE(AfxGetStaticModuleState());|  
|1|경우 (S_OK _AtlModule.GetClassObject (rclsid, riid, ppv) = =)|  
|2|\treturn s_ok이 고,|  
|3|AfxDllGetClassObject (rclsid, riid, ppv);를 반환 합니다.|  
  
 반환 되는 줄은 각각에 대 한 `GetCodeForDllGetClassObject` 선행 탭 추가 (`\t`) 및 후행 "CR-LF" (캐리지 리턴-줄 바꿈) 문자 쌍 (`\r\n`).  
  
## <a name="example"></a>예제  
  
```  
// Get the lines numbered 1 and 2 above  
GetCodeForDllGetClassObject(1, 2)  
  
// returns the following string  
// "\tif (S_OK == _AtlModule.GetClassObject(rclsid, riid, ppv))\r\n\t\treturn S_OK;\r\n"  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [공용 JScript 함수를 사용 하 여 c + + 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C + + 마법사는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)