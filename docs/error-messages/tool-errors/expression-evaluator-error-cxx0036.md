---
title: 식 계산기 오류 CXX0036 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0036
dev_langs:
- C++
helpviewer_keywords:
- CXX0036
- CAN0036
ms.assetid: 383404be-df5b-4eec-b113-df21bb5d269d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 18e1bf3cda85d7b3d64d51279688a52cec5c0336
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33301686"
---
# <a name="expression-evaluator-error-cxx0036"></a>식 계산기 오류 CXX0036
컨텍스트가 잘못 되었습니다 {...} specification  
  
 이 메시지 컨텍스트 연산자를 사용 하는 데 몇 가지 오류 중 하나로 인해 발생할 수 있습니다 (**{}**).  
  
-   컨텍스트 연산자의 구문 (**{}**) 올바르게 지정 되지 않았습니다.  
  
     컨텍스트 연산자의 구문은 다음과 같습니다.  
  
     {*함수*,*모듈*,*dll*}*식*  
  
     컨텍스트를 지정 하는이 *식*합니다. 컨텍스트 연산자는 형식 변환과 같은 우선 순위 및 사용 현황에 있습니다.  
  
     후행 쉼표는 생략할 수 있습니다. 경우 *함수*, *모듈*, 또는 *dll* 리터럴 쉼표를 포함 전체 이름을 괄호로 묶어야 합니다.  
  
-   함수 이름 철자가 잘못, 또는 지정한 모듈 또는 동적 연결 라이브러리에 존재 하지 않습니다.  
  
     C는 대/소문자 구분 언어 *함수* 원본에 정의 된 대로 정확 하 게 대/소문자 지정 해야 합니다.  
  
-   모듈 또는 DLL을 찾을 수 없습니다.  
  
     지정한 모듈 또는 DLL의 전체 경로 이름을 확인 합니다.  
  
 이 오류는 can0036과 동일 합니다.