---
title: MMWORD | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- MMWORD
dev_langs:
- C++
helpviewer_keywords:
- MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e97b1e58116d633519b1a780928e05862ac1771d
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="mmword"></a>MMWORD
MMX와 SSE (XMM) 지침이 포함 된 64 비트 멀티미디어 피연산자에 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
MMWORD  
```  
  
## <a name="remarks"></a>설명  
 `MMWORD` 형식이입니다.  MMWORD MASM에 추가 되 고, 이전와 동등한 기능 구현할 수도 있습니다.  
  
```  
mov mm0, qword ptr [ebx]  
```  
  
 두 지침 64 비트 피연산자에 대해 작동 하는 동안 `QWORD` 64 비트 부호 없는 정수 형식입니다. 및 `MMWORD` 64 비트 멀티미디어 값의 형식입니다.  
  
 `MMWORD` 동일한 형식으로 표시 하기 위해 [__m64](../../cpp/m64.md)합니다.  
  
## <a name="example"></a>예제  
  
```  
movq     mm0, mmword ptr [ebx]  
```