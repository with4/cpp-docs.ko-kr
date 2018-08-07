---
title: 'Hstring:: Hstring 생성자 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::HString
dev_langs:
- C++
ms.assetid: 6da12785-ed01-4720-a004-667db60298f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a3188e137d3a39fb26ca4151f72073306038e46f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876880"
---
# <a name="hstringhstring-constructor"></a>HString::HString 생성자
HString 클래스의 새 인스턴스를 초기화합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HString(HSTRING hstr = nullptr) throw();  
HString(HString&& other) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `hstr`  
 HSTRING 핸들입니다.  
  
 `other`  
 기존 HString 개체입니다.  
  
## <a name="remarks"></a>설명  
 첫 번째 생성자는 비어 있는 새 HString 개체를 초기화 합니다.  
  
 두 번째 생성자는 기존 값을 새 HString 개체를 초기화 합니다. `other` 매개 변수를 삭제 한 다음는 `other` 매개 변수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [HString 클래스](../windows/hstring-class.md)