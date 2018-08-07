---
title: 여러 설명 블록에는 대상 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- description blocks
- blocks, multiple description
- multiple description blocks
ms.assetid: 8618dcd9-c11d-4562-91a7-0c904ed438a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b88c98fa3debc7bd5cc6a21d1bc9440e9386b988
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380290"
---
# <a name="targets-in-multiple-description-blocks"></a>여러 개의 설명 블록에 포함된 대상
다른 명령을 사용 하 여 둘 이상의 설명 블록에 업데이트를 대상 및 종속 항목 간의 연속 된 두 개의 콜론 (:)을 지정 합니다.  
  
```  
target.lib :: one.asm two.asm three.asm  
    ml one.asm two.asm three.asm  
    lib target one.obj two.obj three.obj  
target.lib :: four.c five.c  
    cl /c four.c five.c  
    lib target four.obj five.obj  
```  
  
## <a name="see-also"></a>참고 항목  
 [대상](../build/targets.md)