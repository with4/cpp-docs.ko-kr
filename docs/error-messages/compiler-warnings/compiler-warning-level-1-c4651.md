---
title: "컴파일러 경고 (수준 1) C4651 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4651
dev_langs:
- C++
helpviewer_keywords:
- C4651
ms.assetid: f1ea82aa-4dc1-4972-b55a-57fdb962f0dd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dce099d657341ebc957c95ab0cd14f508f9e36ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4651"></a>컴파일러 경고(수준 1) C4651
' 정의 ' 미리 컴파일된 헤더에 대 한 있지만 현재 컴파일에 대 한 지정  
  
 미리 컴파일된 헤더를 생성할 때에 있지만이 컴파일은 정의 지정 합니다.  
  
 미리 컴파일된 헤더에 있지만 코드의 나머지 부분 정의가 적용 됩니다.  
  
 미리 컴파일된 헤더 /DSYMBOL 빌드된 경우 컴파일러 /Yu 컴파일 /DSYMBOL 없는 경우이 경고를 생성 합니다.  이 경고를 해결 /DSYMBOL /Yu 명령줄에 추가 합니다.