---
title: Varargs | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: aac0c54b-0a2d-4a22-b1de-ee41381a3eb1
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8492610721846e8252cbe71b358e428a2aaf024f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="varargs"></a>Varargs
Varargs (예를 들어 줄임표 인수)를 통해 매개 변수를 전달 하는 경우 기본적으로 일반 매개 변수 전달 다섯 번째 및 이후의 인수를 모두 포함 하 여 적용 합니다. 다시 호출 수신자의 인수의 주소를 덤프 하 합니다. 부동 소수점 값, 정수 및 부동 소수점 레지스터를 모두 포함 됩니다 부동 소수점 값 호출 수신자에 게 정수 레지스터의 값이 필요한 경우.  
  
## <a name="see-also"></a>참고 항목  
 [호출 규칙](../build/calling-convention.md)