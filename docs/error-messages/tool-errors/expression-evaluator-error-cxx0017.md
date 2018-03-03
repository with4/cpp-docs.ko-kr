---
title: "식 계산기 오류 CXX0017 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- CXX0017
dev_langs:
- C++
helpviewer_keywords:
- CAN0017
- CXX0017
ms.assetid: af74db02-a64d-49ca-8363-3e044a107580
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e769e9886168c9f19ad110c48d848a9b84ab8aac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluator-error-cxx0017"></a>식 계산기 오류 CXX0017
기호를 찾을 수합니다  
  
 식에 지정 된 기호를 찾을 수 없습니다.  
  
 이 오류의 한 가지 가능한 원인은 기호 이름에 소문자 일치 하지 않습니다. C 및 c + +는 대/소문자 구분 언어, 때문에 정확한 경우 원본에 정의 된 기호 이름을 지정 합니다.  
  
 이 오류는 디버깅 하는 동안 변수를 감시 하기 위해 변수 형식을 캐스팅 하려고 할 때 발생할 수 있습니다. `typedef` 는 형식에 대 한 새 이름을 선언 되지만 새 형식을 정의 하지 않습니다. 디버거에서 디버거는 정의 된 형식 이름이 필요 합니다.  
  
 이 오류는 can0017과 동일 합니다.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>아래의 해결 방법 따라 수정합니다.  
  
1.  기호가 사용 되는 위치는 프로그램의 지점에서 이미 선언 되어 있는지 확인 합니다.  
  
2.  실제 형식 이름을 사용 하 여 변수를 캐스팅 하면 디버거에서 아닌 `typedef`-정의 된 이름입니다.