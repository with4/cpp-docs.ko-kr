---
title: importidl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.importidl
dev_langs:
- C++
helpviewer_keywords:
- importidl attribute
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1de680b2598a9439338986c283a4041482642fa0
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40015760"
---
# <a name="importidl"></a>importidl
생성된 된.idl 파일에 지정 된.idl 파일을 삽입합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
[ importidl(  
   idl_file  
) ];  
```  
  
### <a name="parameters"></a>매개 변수  
 *idl_file*  
 응용 프로그램에 대해 생성 되는.idl 파일에 병합 하려는.idl 파일의 이름을 식별 합니다.  
  
## <a name="remarks"></a>설명  
 합니다 **importidl** 라이브러리 블록 외부에서 단면을 배치 하는 c + + 특성 (에서 *idl_file*) 프로그램의 생성 된.idl 파일을 라이브러리 섹션 (에서 *idl_file*) 프로그램의 부분을 라이브러리로.idl 파일을 생성 합니다.  
  
 사용 하려는 **importidl**, 예를 들어, 생성 된.idl 파일을 사용 하 여 직접 코딩 된.idl 파일을 사용 하려는 경우.  
  
## <a name="example"></a>예  
  
```cpp  
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