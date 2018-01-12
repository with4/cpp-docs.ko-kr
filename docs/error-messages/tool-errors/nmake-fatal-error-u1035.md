---
title: "NMAKE 심각한 오류 U1035 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: U1035
dev_langs: C++
helpviewer_keywords: U1035
ms.assetid: 68f0cc59-007e-4109-ac30-7ac4ac447e6d
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0d7730f882b40c24822cb4b8e2c6a12147cacf2d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1035"></a>NMAKE 심각한 오류 U1035
구문 오류: 필요 합니다. ':' 또는 '=' 구분 기호  
  
 콜론 (**:**) 또는 등호 (**=**)가 필요 합니다.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면  
  
1.  콜론 대상을 따르지 않습니다.  
  
2.  단일 문자 대상을 뒤에 콜론과 (예: a:) 공간이 없습니다. NMAKE는 드라이브 사양으로 해석 합니다.  
  
3.  콜론 유추 규칙을 따르지 않습니다.  
  
4.  매크로 정의 등호 오지 않았습니다.  
  
5.  백슬래시 뒤에 문자가 (**\\**) 새 줄에 명령을 계속 하는 데 사용 된입니다.  
  
6.  문자열이는 NMAKE 구문 규칙을 따르지 않는 표시 되었습니다.  
  
7.  메이크파일의 워드 프로세서에서 형식이 지정 되었습니다.