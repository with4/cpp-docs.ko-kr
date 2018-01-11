---
title: "식 계산기 오류 CXX0025 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0025
dev_langs: C++
helpviewer_keywords:
- CAN0025
- CXX0025
ms.assetid: 3e2fb541-63b3-46ac-9f93-3dadb253bcf6
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3f4154ca0aa0dcebecce40ed60420be0da6de456
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluator-error-cxx0025"></a>식 계산기 오류 CXX0025
연산자에는 구조체/공용 구조체가 필요합니다.  
  
 식을 사용 하는 연산자 `struct` 또는 **union** 형식이 아닌 식에 적용 된는 `struct` 또는 **union**합니다.  
  
 클래스, 구조체 또는 공용 구조체 변수의 구성 요소는 정규화 된 이름이 있어야 합니다. 구성 요소는 완전 한 사양 없이 입력할 수 없습니다.  
  
 이 오류는 can0025와 동일 합니다.