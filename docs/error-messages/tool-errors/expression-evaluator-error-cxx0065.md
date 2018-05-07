---
title: 식 계산기 오류 CXX0065 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0065
dev_langs:
- C++
helpviewer_keywords:
- CAN0065
- CXX0065
ms.assetid: aac68f87-0b90-4c19-afa6-1c587625a5fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 78c25c9c6bde27219f10e4047dc7a6ab416f55d5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="expression-evaluator-error-cxx0065"></a>식 계산기 오류 CXX0065
변수에 스택 프레임이 필요합니다.  
  
 현재 범위 내에 존재 하지만 아직 만들지 않은 변수 식에 포함 되어 있습니다.  
  
 이 오류는 프롤로그 함수 하지만 아직 함수에 대 한 스택 프레임 설정의 한 단계씩 또는 함수에 대 한 종료 코드를 실행 하는 경우에 발생할 수 있습니다.  
  
 식을 계산 하기 전에 스택 프레임 체결 될 때까지 프롤로그 코드를 단계별로 실행 합니다.  
  
 이 오류는 can0065와 동일 합니다.