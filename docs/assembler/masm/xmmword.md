---
title: XMMWORD | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- XMMWORD
dev_langs:
- C++
helpviewer_keywords:
- XMMWORD directive
ms.assetid: 18026d32-5cab-403e-ad7e-382fb41aa9b8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6844ab0d83fec2ed78a72238c510906aa7ecc8d9
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="xmmword"></a>XMMWORD
MMX와 SSE (XMM) 지침이 포함 된 128 비트 멀티미디어 피연산자에 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
XMMWORD  
```  
  
## <a name="remarks"></a>설명  
 `XMMWORD` 동일한 형식으로 표시 하기 위해 [__m128](../../cpp/m128.md)합니다.  
  
## <a name="example"></a>예  
  
```  
movdqa   xmm0, xmmword ptr [ebx]  
```