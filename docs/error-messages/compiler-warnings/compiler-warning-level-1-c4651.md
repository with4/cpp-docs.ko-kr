---
title: 컴파일러 경고 (수준 1) C4651 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4651
dev_langs:
- C++
helpviewer_keywords:
- C4651
ms.assetid: f1ea82aa-4dc1-4972-b55a-57fdb962f0dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0015102a44b71f342b125532d20849590157ee0c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33283369"
---
# <a name="compiler-warning-level-1-c4651"></a>컴파일러 경고(수준 1) C4651
' 정의 ' 미리 컴파일된 헤더에 대 한 있지만 현재 컴파일에 대 한 지정  
  
 미리 컴파일된 헤더를 생성할 때에 있지만이 컴파일은 정의 지정 합니다.  
  
 미리 컴파일된 헤더에 있지만 코드의 나머지 부분 정의가 적용 됩니다.  
  
 미리 컴파일된 헤더 /DSYMBOL 빌드된 경우 컴파일러 /Yu 컴파일 /DSYMBOL 없는 경우이 경고를 생성 합니다.  이 경고를 해결 /DSYMBOL /Yu 명령줄에 추가 합니다.