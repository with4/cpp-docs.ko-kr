---
title: 'Asyncbase:: Oncancel 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::OnCancel
dev_langs:
- C++
helpviewer_keywords:
- OnCancel method
ms.assetid: 4bd0b68e-a9df-4913-9f6c-e093ed55c3f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b648718c715a43befbc5ead828c810dbfa92d120
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39646876"
---
# <a name="asyncbaseoncancel-method"></a>AsyncBase::OnCancel 메서드
파생된 클래스에서 재정의 되 면 비동기 작업을 취소 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
virtual void OnCancel(  
   void  
) = 0;  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)   
 [AsyncBase::Cancel 메서드](../windows/asyncbase-cancel-method.md)