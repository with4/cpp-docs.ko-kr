---
title: "컴파일러 오류 C2834 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2834
dev_langs: C++
helpviewer_keywords: C2834
ms.assetid: 28f9f6eb-ab2a-4e64-aaaa-9d14f955de41
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 616bb6fe351c7575bf04f319390d0a3cfcd3cc8a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2834"></a>컴파일러 오류 C2834
'operator 연산자' 전역으로 한정 되어야 합니다.  
  
 `new` 및 `delete` 연산자는 클래스에 연결 된 위치입니다. 범위 결정의 버전을 선택 하는 데 사용할 수 없습니다 `new` 또는 `delete` 다른 클래스에서 합니다. 여러 형식의 구현 하는 `new` 또는 `delete` 연산자를 추가 형식 매개 변수가 있는 연산자의 버전을 만듭니다.