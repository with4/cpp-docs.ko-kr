---
title: ATL 전역 변수 | Microsoft Docs
ms.custom: ''
ms.date: 12/06/2017
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ATLBASE/_pAtlModule
dev_langs:
- C++
helpviewer_keywords:
- global variables, ATL
- _pAtlModule
ms.assetid: e881a319-99ca-4f5d-8a0b-34b3dcd0f37f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4664c99eb49b57f258be399c042fa14b60bbecdf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356481"
---
# <a name="atl-global-variables"></a>ATL 전역 변수

## <a name="patlmodule"></a>_pAtlModule  
현재 모듈에 대 한 포인터를 저장 하는 전역 변수입니다.  

```cpp  
__declspec(selectany) CAtlModule * _pAtlModule  
```  
### <a name="remarks"></a>설명  
CComModule (이제 사용 되지 않음) 클래스 Visual c + + 6.0에서 제공 하는 기능을 제공 하기이 전역 변수에 대 한 메서드를 사용할 수 있습니다.

### <a name="example"></a>예제  

```cpp  
LONG lLocks = _pAtlModule->GetLockCount();  
```  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  

