---
title: "가져오기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.import
dev_langs:
- C++
helpviewer_keywords:
- import attribute
ms.assetid: ebf07cae-39fb-4047-8b57-54af0a9a83de
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 011cabb37f388d4be6a9a69f685a7c711f0209a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="import"></a>import
주 프로그램 IDL에서 참조 하려는 정의 포함 하는 다른.idl,.odl, 또는 헤더 파일을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      [ import(  
   idl_file  
) ];  
```  
  
#### <a name="parameters"></a>매개 변수  
 `idl_file`  
 현재 프로젝트의 형식 라이브러리로 가져오려는.idl 파일의 이름입니다.  
  
## <a name="remarks"></a>설명  
 **가져올** c + + 특성을 사용 하면는 `#import` 문 아래에 배치 하는 `import "docobj.idl"` 생성 된.idl 파일의 문입니다. **가져올** 특성와 동일한 기능에는 [가져올](http://msdn.microsoft.com/library/windows/desktop/aa367047) MIDL 특성과 합니다.  
  
 **가져올** 만 특성; 프로젝트에 의해 생성 되는.idl 파일에 지정된 된 파일을 배치는 **가져올** 특성 사용 소스 코드에서 지정한 파일에 구문 호출 프로젝트입니다.  구문에 지정된 된 파일에서 프로젝트의 소스 코드를 호출 하려면 사용 하거나 [#import](../preprocessor/hash-import-directive-cpp.md) 및 `embedded_idl` 특성 또는 있습니다.h 파일을 포함할 수는 `idl_file`.h 파일이 있는 경우, 합니다.  
  
## <a name="example"></a>예  
 다음 예를 참조하십시오.  
  
```  
// cpp_attr_ref_import.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[import(import.idl)];  
```  
  
 생성된 된.idl 파일에 다음 코드를 생성합니다.  
  
```  
import "docobj.idl";  
import "import.idl";  
  
[ uuid(EED3644C-8488-3ECD-BA97-147DB3CDB499), version(1.0) ]  
library MyLib {  
   importlib("stdole2.tlb");  
   importlib("olepro32.dll");  
...  
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
 [importidl](../windows/importidl.md)   
 [importlib](../windows/importlib.md)   
 [포함](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)   
