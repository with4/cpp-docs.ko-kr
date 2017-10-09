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
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: c097f213d790a992d12a8c358282a5340fce52c4
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

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
