---
title: 심각한 오류 C1067 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1067
dev_langs:
- C++
helpviewer_keywords:
- C1067
ms.assetid: e2c94be6-4573-4571-aac9-73d657fe9f96
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 89ac7084e92f7f2ed496a4c1572e94a4fa46862f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229094"
---
# <a name="fatal-error-c1067"></a>심각한 오류 C1067
컴파일러 한계: 형식 레코드 크기의 64k 한도 초과 했습니다  
  
 이 오류는 기호에는 트 데코 레이 된 이름이 247 자를 초과 하는 경우에 발생할 수 있습니다.  를 해결 하려면 기호 이름을 줄이십시오.  
  
 컴파일러가 디버그 정보를 생성할 때 형식 소스 코드에서 형식을 정의 하는 레코드를 내보냅니다.  예를 들어 유형 레코드에는 간단한 구조와 함수에 인수 목록이 포함 됩니다.  이러한 형식 레코드의 일부 큰 목록 수 있습니다.  
  
 모든 형식 레코드의 크기에 64k 제한이 있습니다.  64k 한도 초과 하는 경우이 오류가 발생 합니다.  
  
 C1067 기호가 이름이 긴 또는 클래스, 구조체 또는 공용 구조체에 멤버가 너무 많은 경우에 발생할 수 있습니다.