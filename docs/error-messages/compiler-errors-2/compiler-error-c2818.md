---
title: "컴파일러 오류 C2818 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2818
dev_langs: C++
helpviewer_keywords: C2818
ms.assetid: 715fc7c9-0c6d-452b-b7f5-1682cea5e907
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f409acd9ba18972ca414c81cbcabd279e8903bcd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2818"></a>컴파일러 오류 C2818
오버로드된 'operator ->'는 'type' 형식을 통해 재귀적으로 적용됩니다.  
  
 재귀를 포함 하는 클래스 멤버 액세스 연산자의 재정의 `return` 문. 다시 정의 하는 `->` 재귀 연산자를 이동 해야 재귀 루틴의 연산자에서 호출 하는 별도 함수에 함수를 재정의 합니다.