---
title: 'Semaphore:: operator = 연산자 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: ea19839f-91f0-4b00-a35b-5728fcba4981
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 25287e642bd368470b207ed237f44ca70773064e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892529"
---
# <a name="semaphoreoperator-operator"></a>Semaphore::operator= 연산자
Semaphore 개체에서 현재 Semaphore 개체에 지정된 된 핸들을 이동합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Semaphore& operator=(  
   _Inout_ Semaphore&& h  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `h`  
 Semaphore 개체에 Rvalue 참조입니다.  
  
## <a name="return-value"></a>반환 값  
 현재 Semaphore 개체에 대 한 참조입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers
 
 ## <a name="see-also"></a>참고 항목
 [Semaphore 클래스](../windows/semaphore-class.md)