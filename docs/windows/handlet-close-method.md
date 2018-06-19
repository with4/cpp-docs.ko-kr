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
ms.openlocfilehash: 4f0c1e47420106651cfe0526d6d212e9819a72ff
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873253"
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