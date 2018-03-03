---
title: "컴파일러 경고 (수준 1) C4027 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4027
dev_langs:
- C++
helpviewer_keywords:
- C4027
ms.assetid: f30d57b9-20c4-4284-8686-566d9f0ca7fc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 22a8a1794a5b80af58a26f07bf58d11a77cb1d5a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4027"></a>컴파일러 경고(수준 1) C4027
정식 매개 변수 목록을 사용하지 않고 함수를 선언했습니다.  
  
 함수 선언에 정식 매개 변수가 없지만 함수 정의에 정식 매개 변수가 있거나 호출에 실제 매개 변수가 있습니다. 이 함수에 대한 후속 호출은 함수가 함수 정의 또는 호출에 있는 형식의 실제 매개 변수를 사용한다고 가정합니다.