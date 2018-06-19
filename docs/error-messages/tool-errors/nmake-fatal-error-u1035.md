---
title: NMAKE 심각한 오류 U1035 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1035
dev_langs:
- C++
helpviewer_keywords:
- U1035
ms.assetid: 68f0cc59-007e-4109-ac30-7ac4ac447e6d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6bb32f815345b933ad6a65a0c8c1ec8ad59cbe81
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322798"
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