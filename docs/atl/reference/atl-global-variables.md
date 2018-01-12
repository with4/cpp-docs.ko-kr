---
title: "ATL 전역 변수 | Microsoft Docs"
ms.custom: 
ms.date: 12/06/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: ATLBASE/_pAtlModule
dev_langs: C++
helpviewer_keywords:
- global variables, ATL
- _pAtlModule
ms.assetid: e881a319-99ca-4f5d-8a0b-34b3dcd0f37f
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bcf9a88e57d351a3fb6647f6deea3eccbad33bf8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="atl-global-variables"></a>ATL 전역 변수

## <a name="patlmodule"></a>_pAtlModule  
현재 모듈에 대 한 포인터를 저장 하는 전역 변수입니다.  

```cpp  
__declspec(selectany) CAtlModule * _pAtlModule  
```  
### <a name="remarks"></a>설명  
CComModule (이제 사용 되지 않음) 클래스 Visual c + + 6.0에서 제공 하는 기능을 제공 하기이 전역 변수에 대 한 메서드를 사용할 수 있습니다.

### <a name="example"></a>예  

```cpp  
LONG lLocks = _pAtlModule->GetLockCount();  
```  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  

