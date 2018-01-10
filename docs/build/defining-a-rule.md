---
title: "규칙 정의 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, inference rules
- defining inference rules
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c0d6ca616e3685db36d6d24b339a860eab4c6150
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="defining-a-rule"></a>규칙 정의
*fromext* 종속 파일의 확장을 나타내는 및 *toext* 대상 파일의 확장을 나타냅니다.  
  
```  
.fromext.toext:  
   commands  
```  
  
## <a name="remarks"></a>설명  
 확장은 대/소문자 구분 하지 않습니다. 매크로 나타내기 위해 호출 될 수 있습니다 *fromext* 및 *toext*; 전처리 하는 동안 매크로가 확장 됩니다. 마침표 (.) 이전 *fromext* 줄의 시작 부분에 표시 되어야 합니다. 콜론 (:) 앞 공백이 나 탭 0 개 이상 있습니다. 공백 또는 탭, 세미콜론 (;) 명령을 지정 하려면, 메모를 지정 하려면 숫자 기호 (#) 또는 줄 바꿈 문자를 통해서만 수행할 수 있습니다. 다른 공백이 있어서는 안 됩니다. 명령이 설명 블록에서와 같이 지정 됩니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
 [규칙에서 경로 검색](../build/search-paths-in-rules.md)  
  
## <a name="see-also"></a>참고 항목  
 [유추 규칙](../build/inference-rules.md)