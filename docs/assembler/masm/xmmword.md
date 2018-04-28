---
title: XMMWORD | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- XMMWORD
dev_langs:
- C++
helpviewer_keywords:
- XMMWORD directive
ms.assetid: 18026d32-5cab-403e-ad7e-382fb41aa9b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f8fd8e6c82a3275161e519eeead490473e8d64ab
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="xmmword"></a>XMMWORD
MMX와 SSE (XMM) 지침이 포함 된 128 비트 멀티미디어 피연산자에 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
XMMWORD  
```  
  
## <a name="remarks"></a>설명  
 `XMMWORD` 동일한 형식으로 표시 하기 위해 [__m128](../../cpp/m128.md)합니다.  
  
## <a name="example"></a>예제  
  
```  
movdqa   xmm0, xmmword ptr [ebx]  
```