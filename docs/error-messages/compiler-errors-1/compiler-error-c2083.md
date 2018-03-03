---
title: "컴파일러 오류 C2083 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2083
dev_langs:
- C++
helpviewer_keywords:
- C2083
ms.assetid: 5fc4f931-eab6-4d8d-a3ee-3b8e11e64b18
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 50f269caa36d3111d59295f066f37223254d87aa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2083"></a>컴파일러 오류 C2083
struct/union 비교가 잘못되었습니다.  
  
 구조체 또는 공용 구조체는 다른 사용자 정의 형식과 직접 비교됩니다. 이는 비교 연산자를 정의했거나 스칼라 형식에 대한 변환이 존재하지 않는 한 허용되지 않습니다.