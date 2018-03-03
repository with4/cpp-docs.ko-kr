---
title: "컴파일러 오류 C2410 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2410
dev_langs:
- C++
helpviewer_keywords:
- C2410
ms.assetid: b69b2de1-56f3-4ebc-8913-04ac57ffe8a1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3cd5dfa7b33f5af5c57f6479170a7a56df39a0e9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2410"></a>컴파일러 오류 C2410
'identifier': '컨텍스트'의 멤버 이름이 모호  
  
 식별자가 둘 이상의 구조 또는이 컨텍스트에서 공용 구조체의 멤버가 있습니다.  
  
 오류를 발생 시킨 피연산자에서 구조체 또는 공용 구조체 지정자를 사용 합니다. 구조체 또는 공용 구조체 지정자는 형식 식별자 `struct` 또는 `union` (한 `typedef` 이름이 나 구조체 또는 참조 되는 공용 구조체와 동일한 형식의 변수). 지정자는 피연산자를 사용 하는 첫 번째 멤버 선택 연산자 (.)의 왼쪽된 피연산자 이어야 합니다.