---
title: "Handlet:: Close 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: 1b9d597c-abcf-4028-a068-0344560009f6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c2edd3fee9893c72685eb334bf4b361997646b7d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="handletclose-method"></a>HandleT::Close 메서드
현재 HandleT 개체를 닫습니다.  
  
## <a name="syntax"></a>구문  
  
```  
void Close();  
```  
  
## <a name="remarks"></a>설명  
 현재 HandleT를 기반으로 하는 핸들이 닫히고 HandleT가 유효하지 않은 상태로 설정됩니다.  
  
 핸들이 제대로 닫히지 않은 경우 호출 스레드에서 예외가 발생합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [HandleT 클래스](../windows/handlet-class.md)