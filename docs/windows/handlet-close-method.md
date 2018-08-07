---
title: 'Handlet:: Close 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: 1b9d597c-abcf-4028-a068-0344560009f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 69f3f2c756d158954676f6fc42941b1b80f4345e
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569920"
---
# <a name="handletclose-method"></a>HandleT::Close 메서드
현재 닫습니다 **HandleT** 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
void Close();  
```  
  
## <a name="remarks"></a>설명  
 현재의 기반이 되는 핸들 **HandleT** 닫혀 하며 **HandleT** 잘못 된 상태로 설정 됩니다.  
  
 핸들이 제대로 닫히지 않은 경우 호출 스레드에서 예외가 발생합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [HandleT 클래스](../windows/handlet-class.md)