---
title: 심각한 오류 C1900 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1900
dev_langs:
- C++
helpviewer_keywords:
- C1900
ms.assetid: 3aaa583b-4c1a-45de-aa34-527d806f2cb5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da7cdd5601785f43748ec87d3219f43728536855
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1900"></a>심각한 오류 C1900
'tool1' 버전 'number1'과(와) 'tool2' 버전 'number2' 사이에 II이 일치하지 않습니다.  
  
 컴파일러의 여러 패스에서 실행되는 도구가 일치하지 않습니다. ***number1*** 및 ***number2*** 파일에 날짜를 참조 합니다. 예를 들어 패스 1에서는 컴파일러 프런트 엔드가 실행되고(c1.dll) 패스 2에서는 컴파일러 백 엔드가 실행됩니다(c2.dll) 파일의 날짜는 일치해야 합니다.  
  
 이 문제를 해결하려면 Visual Studio에 모든 업데이트가 적용되었는지 확인합니다. 문제가 지속 되 면 사용 **프로그램 및 기능** 을 복구 하거나 Visual Studio를 다시 설치 하려면 Windows 제어판에서.