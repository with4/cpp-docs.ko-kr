---
title: "매크로의 특수 문자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: special characters, in NMAKE macros
ms.assetid: c0a06cfc-7103-4ee2-a585-e8f6e85dccd7
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 648122a9c8f3cf97d08128e6e12090ebc12631d9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="special-characters-in-macros"></a>매크로의 특수 문자
숫자 기호 (#) 후 정의 설명을 지정 합니다. 매크로에서 리터럴 숫자 기호를 지정 하려면 사용 하 여 캐럿 (^)에서 같이 ^ #.  
  
 달러 기호 ($)는 매크로 호출을 지정 합니다. $ 리터럴을 지정 하려면 $$를 사용 합니다.  
  
 확장 되는 새 줄을 정의 하려면 백슬래시와 줄 끝 (\\). 매크로 호출 하면 백슬래시와 줄 바꿈 문자가 공백으로 바뀝니다. 줄의 끝에 백슬래시를 지정 하려면 앞에 캐럿 (^)을 사용 하거나 주석 지정자 뒤 (#).  
  
 리터럴 줄 바꿈 문자를 지정 하려면 줄 끝에 캐럿 (^)으로:  
  
```  
CMDS = cls^  
dir  
```  
  
## <a name="see-also"></a>참고 항목  
 [NMake 매크로 정의](../build/defining-an-nmake-macro.md)