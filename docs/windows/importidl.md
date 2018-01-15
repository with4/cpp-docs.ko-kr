---
title: importidl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.importidl
dev_langs: C++
helpviewer_keywords: importidl attribute
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cd3fb56898107b1eca7cd30e06d75d253a02655e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="importidl"></a>importidl
생성된 된.idl 파일에 지정 된.idl 파일을 삽입합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      [ importidl(  
   idl_file  
) ];  
```  
  
#### <a name="parameters"></a>매개 변수  
 `idl_file`  
 응용 프로그램에 대해 생성 되는.idl 파일과 병합 하려는.idl 파일의 이름을 식별 합니다.  
  
## <a name="remarks"></a>설명  
 **importidl** 라이브러리 블록 밖에 서 단면을 배치 하는 c + + 특성 (에서 `idl_file`) 프로그램의 생성 된.idl 파일 및 라이브러리 섹션 (에서 `idl_file`) 프로그램의의 라이브러리 섹션에 생성 된.idl 파일입니다.  
  
 사용 하려는 경우 **importidl**, 예를 들어 직접 코딩 된.idl 파일 생성 된.idl 파일을 사용 하려는 경우.  
  
## <a name="example"></a>예  
  
```  
// cpp_attr_ref_importidl.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[importidl("import.idl")];  
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
 [컴파일러 특성](../windows/compiler-attributes.md)   
 [독립 실행형 특성](../windows/stand-alone-attributes.md)   
 [가져오기](../windows/import.md)   
 [importlib](../windows/importlib.md)   
 [포함](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)   
