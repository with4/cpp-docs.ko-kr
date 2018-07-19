---
title: 컴파일러 오류 C2585 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2585
dev_langs:
- C++
helpviewer_keywords:
- C2585
ms.assetid: 05bb1a9c-28fb-4a88-a1b5-aea85ebdee1c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ab812a4b6621acb28a4df636056598047f5c21e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33230163"
---
# <a name="compiler-error-c2585"></a>컴파일러 오류 C2585
'type' 명시적 변환이 모호 합니다.  
  
 형식을 변환 하 여 둘 이상의 결과 생성할 수 있습니다.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면  
  
1.  다중 상속 기반 클래스 또는 구조체 형식에서 변환 합니다. 변환 함수 또는 연산자 유형을 동일한 기본 클래스를 두 번 이상 상속 하는 경우 범위 결정 사용 해야 합니다 (`::`) 변환에 사용할를 상속 된 클래스 중 하나로 지정할 수 있습니다.  
  
2.  변환 연산자 및 생성자가 정의 된 동일한 변환을 수행 합니다.