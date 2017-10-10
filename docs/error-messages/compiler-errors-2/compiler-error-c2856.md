---
title: "컴파일러 오류 C2856 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2856
dev_langs:
- C++
helpviewer_keywords:
- C2856
ms.assetid: fe616c51-124e-49e3-9dd8-883ec1660680
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 69b2cdf1e7f3000ef26706c937bff33266ea087a
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2856"></a>컴파일러 오류 C2856
\#pragma hdrstop #if 블록 내에 있을 수 없습니다.  
  
 `hdrstop` pragma는 조건부 컴파일 블록의 본문 안에 배치할 수 없습니다.  
  
 이동 된 `#pragma hdrstop` 문을에 포함 되지 않은 영역에는 `#if/#endif` 블록입니다.
