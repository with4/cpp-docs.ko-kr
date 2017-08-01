---
title: "문자 시퀀스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 1e6961a9-150e-4c13-b427-9af4b6a1fb7a
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 67ddf6a6712e0c98ea7b7866b3267d56308a5b5c
ms.contentlocale: ko-kr
ms.lasthandoff: 05/18/2017

---
# <a name="character-sequences"></a>문자 시퀀스
**ANSI 3.8.2** 소스 파일 문자 시퀀스의 매핑  
  
 전처리기 문은 이스케이프 시퀀스가 지원되지 않는 경우를 제외하고 소스 파일 문과 같은 문자 설정을 사용합니다.  
  
 따라서 include 파일에 대한 경로를 지정하려면 백슬래시를 하나만 사용해야 합니다.  
  
```  
#include "path1\path2\myfile"  
```  
  
 소스 코드 내에서는 두 개의 백슬래시가 필요합니다.  
  
```  
fil = fopen( "path1\\path2\\myfile", "rt" );  
```  
  
## <a name="see-also"></a>참고 항목  
 [전처리 지시문](../c-language/preprocessing-directives.md)
