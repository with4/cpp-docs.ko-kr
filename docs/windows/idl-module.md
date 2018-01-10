---
title: idl_module | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.idl_module
dev_langs: C++
helpviewer_keywords: idl_module attribute
ms.assetid: 3578b337-e38a-4334-b747-15404c02dbc0
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f052692686149b247a50c0d89e77797f4f48fab3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="idlmodule"></a>idl_module
.Dll 파일에는 진입점을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
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
  
#### <a name="parameters"></a>매개 변수  
 **name**  
 .Idl 파일에 표시 되는 코드 블록에 대 한 사용자 정의 이름입니다.  
  
 **dllname** (선택 사항)  
 내보내기를 포함 하는.dll 파일입니다.  
  
 `uuid`(선택 사항)  
 고유한 ID입니다.  
  
 **helpstring** (선택 사항)  
 형식 라이브러리에 설명 하는 데 사용 되는 문자 문자열입니다.  
  
 **helpstringcontext** (선택 사항)  
 .Hlp 또는.chm 파일 도움말 항목의 ID입니다.  
  
 **helpcontext** (선택 사항)  
 이 형식 라이브러리에 대한 도움말 ID입니다.  
  
 **hidden** (선택 사항)  
 라이브러리가 표시 되지 않도록 하는 매개 변수입니다. 자세한 내용은 [hidden](http://msdn.microsoft.com/library/windows/desktop/aa366861) MIDL 특성을 참조하세요.  
  
 ***제한 된*** (선택 사항)  
 라이브러리의 멤버를 임의로 호출할 수 없습니다. 자세한 내용은 [restricted](http://msdn.microsoft.com/library/windows/desktop/aa367157) MIDL 특성을 참조하세요.  
  
 *함수 선언*  
 사용자가 정의 하는 함수입니다.  
  
## <a name="remarks"></a>설명  
 `idl_module` c + + 특성.dll 파일에서 가져올 수 있는.dll 파일에는 진입점을 지정할 수 있습니다.  
  
 **idl_module** 특성에 유사한 기능으로는 [모듈](http://msdn.microsoft.com/library/windows/desktop/aa367099) MIDL 특성입니다.  
  
 .Idl 파일로의 라이브러리 블록에서 DLL 진입점을 배치 하 여.dll 파일에서 내보낼 수 있는 COM 개체에서 모든 항목을 내보낼 수 있습니다.  
  
 사용자를 사용 해야 `idl_module` 두 단계를 수행에서 합니다. 첫째, 이름/DLL 쌍을 정의 해야 합니다. 그런 다음 사용 하는 경우 `idl_module` 진입점을 지정 하려면 이름 및 추가 특성을 지정 합니다.  
  
## <a name="example"></a>예  
 다음 코드에서는 사용 하 여 `idl_module` 특성:  
  
```  
// cpp_attr_ref_idl_module.cpp  
// compile with: /LD  
[idl_quote("midl_pragma warning(disable:2461)")];  
[module(name="MyLibrary"), idl_module(name="MyLib", dllname="xxx.dll")];  
[idl_module(name="MyLib"), entry(4), usesgetlasterror]  
void FuncName(int i);  
```  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|원하는 위치|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [독립 실행형 특성](../windows/stand-alone-attributes.md)   
 [entry](../windows/entry.md)   
