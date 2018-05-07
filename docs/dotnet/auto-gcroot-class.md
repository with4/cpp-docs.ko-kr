---
title: auto_gcroot 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr::auto_gcroot
- msclr.auto_gcroot
- auto_gcroot
dev_langs:
- C++
helpviewer_keywords:
- auto_gcroot
ms.assetid: b5790912-265d-463e-a486-47302e91042a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b6afad3450aff2a9243b3e4a480a374fbcd14fc7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="autogcroot-class"></a>auto_gcroot 클래스
자동 리소스 관리 (같은 [auto_ptr 클래스](../standard-library/auto-ptr-class.md))는 네이티브 형식에 가상 핸들을 포함 하 여 사용할 수 있는 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename _element_type>  
class auto_gcroot;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `_element_type`  
 포함할 관리 되는 형식입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더 파일** \<msclr\auto_gcroot.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>참고 항목  
 [auto_gcroot](../dotnet/auto-gcroot.md)   
 [auto_gcroot 멤버](../dotnet/auto-gcroot-members.md)   
 [방법: 네이티브 형식으로 핸들 선언](../dotnet/how-to-declare-handles-in-native-types.md)   
 [auto_handle 클래스](../dotnet/auto-handle-class.md)