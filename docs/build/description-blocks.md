---
title: 설명 블록 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- description blocks
- NMAKE program, description blocks
- blocks, description
ms.assetid: 1321f228-d389-40ac-b0cd-4f6e9293602b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0784f08c479a8c8f3968ef61a01431cd9e0ca71e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="description-blocks"></a>설명 블록
설명 블록은 필요에 따라 뒤 명령 블록이 연결선입니다.  
  
```  
targets... : dependents...  
    commands...  
```  
  
 종속 줄 하나 이상의 대상 및 0 개 이상의 종속 항목을 지정합니다. 줄의 시작 부분에 대상 이어야 합니다. 콜론 (:)으로 참조 하는 셀에서 별도 대상 공백이 나 탭 허용 됩니다. 줄을 분할 하려면 대상 또는 종속 후 백슬래시 (\)를 사용 합니다. 대상이 없는 경우에 종속 보다 이전의 타임 스탬프 있거나는 [의사 대상](../build/pseudotargets.md), NMAKE 명령을 실행 합니다. 종속 다른 곳에서 대상인 존재 하지 않거나 자체 종속 항목에 대하여 오래 된, 경우 NMAKE 업데이트 현재 종속에서 종속 항목을 업데이트 합니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
 [대상](../build/targets.md)  
  
 [종속 파일](../build/dependents.md)  
  
## <a name="see-also"></a>참고 항목  
 [NMAKE 참조](../build/nmake-reference.md)