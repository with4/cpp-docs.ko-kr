---
title: "대상 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: targets, specifying in NMAKE
ms.assetid: 826ee849-4278-4c6e-97c3-79a2b5fe6463
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 40bb3e7e35b00f6c09cdaf5a87fc558db8324989
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="targets"></a>대상
종속 줄에서 모든 유효한 파일 이름, 디렉터리 이름을 사용 하 여 하나 이상의 대상을 지정 또는 [의사 대상](../build/pseudotargets.md)합니다. 여러 대상이 하나 이상의 공백이 나 탭으로 구분 합니다. 대상은 대/소문자 구분 하지 않습니다. 경로 파일 이름에 허용 됩니다. 대상에는 256 자를 초과할 수 없습니다. 단일 문자를 콜론 앞의 대상이 사용 하는 경우 분리 하면 공간;을 사용 합니다. 그렇지 않으면 NMAKE 문자와 콜론 조합 드라이브 지정자로 해석합니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
 [의사 대상](../build/pseudotargets.md)  
  
 [여러 대상](../build/multiple-targets.md)  
  
 [누적 종속성](../build/cumulative-dependencies.md)  
  
 [여러 설명 블록에는 대상](../build/targets-in-multiple-description-blocks.md)  
  
 [의도 하지 않은 종속성](../build/dependency-side-effects.md)  
  
## <a name="see-also"></a>참고 항목  
 [설명 블록](../build/description-blocks.md)