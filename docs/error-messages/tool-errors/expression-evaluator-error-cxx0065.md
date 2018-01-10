---
title: "식 계산기 오류 CXX0065 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0065
dev_langs: C++
helpviewer_keywords:
- CAN0065
- CXX0065
ms.assetid: aac68f87-0b90-4c19-afa6-1c587625a5fd
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: db01baa10191df50c1f319bf8320263657088d75
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluator-error-cxx0065"></a>식 계산기 오류 CXX0065
변수에 스택 프레임이 필요합니다.  
  
 현재 범위 내에 존재 하지만 아직 만들지 않은 변수 식에 포함 되어 있습니다.  
  
 이 오류는 프롤로그 함수 하지만 아직 함수에 대 한 스택 프레임 설정의 한 단계씩 또는 함수에 대 한 종료 코드를 실행 하는 경우에 발생할 수 있습니다.  
  
 식을 계산 하기 전에 스택 프레임 체결 될 때까지 프롤로그 코드를 단계별로 실행 합니다.  
  
 이 오류는 can0065와 동일 합니다.