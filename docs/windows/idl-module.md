---
title: "idl_module | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.idl_module"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "idl_module attribute"
ms.assetid: 3578b337-e38a-4334-b747-15404c02dbc0
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# idl_module
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

진입점을.dll 파일을 지정합니다.  
  
## 구문  
  
```  
  
      [ idl_module (   
   name=module_name,   
   dllname=dll,   
   uuid="uuid",   
   helpstring="help text",   
   helpstringcontext=helpcontextID,   
   helpcontext=helpcontext,   
   hidden,   
   restricted  
) ]  
function declaration  
```  
  
#### 매개 변수  
 **이름**  
 사용자 정의 이름.idl 파일에 표시 되는 코드 블록입니다.  
  
 **dllname** \(옵션\)  
 내보내기가 포함 된.dll 파일입니다.  
  
 `uuid`\(선택적 요소\)  
 고유한 ID입니다.  
  
 **helpstring** \(옵션\)  
 형식 라이브러리를 설명 하는 데 사용 되는 문자열입니다.  
  
 **helpstringcontext** \(옵션\)  
 .Hlp 또는.chm 파일에 있는 도움말 항목의 ID입니다.  
  
 **가 helpcontext** \(옵션\)  
 이 형식 라이브러리에 대 한 도움말 ID입니다.  
  
 **숨겨진** \(옵션\)  
 라이브러리에 표시 되지 않도록 매개 변수입니다.  참조는  [숨겨진](http://msdn.microsoft.com/library/windows/desktop/aa366861) 에 대 한 자세한 내용은 MIDL 속성입니다.  
  
 ***제한 된***  \(옵션\)  
 라이브러리 멤버를 임의로 호출할 수 없습니다.  참조는  [제한 된](http://msdn.microsoft.com/library/windows/desktop/aa367157) 에 대 한 자세한 내용은 MIDL 속성입니다.  
  
 *함수 선언*  
 사용자가 정의 하는 함수입니다.  
  
## 설명  
 `idl_module` C \+ \+ 특성을 사용 하면.dll 파일을 가져올 수 있습니다 하는.dll 파일의 진입점을 지정 합니다.  
  
 **Idl\_module**  특성에 유사한 기능을가지고 있는  [모듈](http://msdn.microsoft.com/library/windows/desktop/aa367099) MIDL 속성.  
  
 .Idl 파일 라이브러리 블록에서 DLL 진입점을 배치 하 여.dll 파일을 내보낼 수 있는 COM 개체에서 모든 항목을 내보낼 수 있습니다.  
  
 사용 해야 합니다 `idl_module` 두 단계를 거쳐야에서 합니다.  첫째, 이름\/DLL 쌍을 정의 해야 합니다.  그런 다음 사용 하면 `idl_module` 진입점을 지정 하려면 이름 및 추가 특성을 지정 합니다.  
  
## 예제  
 다음 코드를 사용 하는 방법을 보여 줍니다 있는 `idl_module` 특성:  
  
```  
// cpp_attr_ref_idl_module.cpp  
// compile with: /LD  
[idl_quote("midl_pragma warning(disable:2461)")];  
[module(name="MyLibrary"), idl_module(name="MyLib", dllname="xxx.dll")];  
[idl_module(name="MyLib"), entry(4), usesgetlasterror]  
void FuncName(int i);  
```  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|원하는 위치에|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 자세한 내용은  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Stand\-Alone Attributes](../windows/stand-alone-attributes.md)   
 [entry](../windows/entry.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)