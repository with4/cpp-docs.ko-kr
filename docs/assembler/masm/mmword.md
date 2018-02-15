---
title: MMWORD | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- MMWORD
dev_langs:
- C++
helpviewer_keywords:
- MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0570a55dc11994e12acedb85d3ae8015abefb54c
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
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
  
## <a name="example"></a>예  
  
```  
movq     mm0, mmword ptr [ebx]  
```