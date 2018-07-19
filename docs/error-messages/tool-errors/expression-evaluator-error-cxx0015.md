---
title: 식 계산기 오류 CXX0015 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0015
dev_langs:
- C++
helpviewer_keywords:
- CXX0015
- CAN0015
ms.assetid: 35efaf77-d578-48d8-bfc5-fdeb2a46a8b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 945dbda4759fa2989acb0411d1a3216a5e9a036c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33297611"
---
# <a name="expression-evaluator-error-cxx0015"></a>식 계산기 오류 CXX0015
식이 너무 복잡 합니다 (스택 오버플로).  
  
 입력 된 식에는 너무 복잡 하거나 C 식 계산기를 사용할 수 있는 저장소 양에 비해 너무 많이 중첩 되었습니다.  
  
 오버플로 일반적으로 너무 많은 보류 중인 계산으로 인해 발생 합니다.  
  
 계산 식의 다른 부분에 대 한 대기 하는 대신 식의 각 구성 요소는 발견 된 대로 계산 될 수 있도록 다시 정렬 합니다.  
  
 식은 여러 개의 명령을 분해 합니다.  
  
 이 오류는 can0015와 동일 합니다.