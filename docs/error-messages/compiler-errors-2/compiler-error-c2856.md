---
title: 컴파일러 오류 C2856 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2856
dev_langs:
- C++
helpviewer_keywords:
- C2856
ms.assetid: fe616c51-124e-49e3-9dd8-883ec1660680
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ac67538a10d39bc68059b0a7d1aaf73a381abb2a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2856"></a>컴파일러 오류 C2856
\#pragma hdrstop #if 블록 내에 있을 수 없습니다.  
  
 `hdrstop` pragma는 조건부 컴파일 블록의 본문 안에 배치할 수 없습니다.  
  
 이동 된 `#pragma hdrstop` 문을에 포함 되지 않은 영역에는 `#if/#endif` 블록입니다.