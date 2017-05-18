---
title: "32비트 Windows 시간/날짜 서식 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.time
dev_langs:
- C++
helpviewer_keywords:
- 32-bit Windows
ms.assetid: ef1589db-84d7-4b24-8799-7c7a22cfe2bf
caps.latest.revision: 6
author: corob-msft
ms.author: corob
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: bd00adddbf728aae66120fede63e0b6a0c5439a7
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="32-bit-windows-timedate-formats"></a>32비트 Windows 시간/날짜 서식
파일 시간 및 날짜는 부호 없는 정수를 비트 필드로 사용하여 개별적으로 저장됩니다. 파일 시간 및 날짜는 다음과 같이 채워집니다.  
  
### <a name="time"></a>시간  
  
|비트 위치:|0   1   2   3   4|5   6   7   8   9   A|B   C   D   E   F|  
|-------------------|-----------------------|---------------------------|-----------------------|  
|길이:|5|6|5|  
|콘텐츠:|시|분|2초 증가|  
|값 범위:|0-23|0-59|2초 간격으로 0-29|  
  
### <a name="date"></a>날짜  
  
|비트 위치:|0   1   2   3   4   5   6|7   8   9   A|B   C   D   E   F|  
|-------------------|-------------------------------|-------------------|-----------------------|  
|길이:|7|4|5|  
|콘텐츠:|년|월|일|  
|값 범위:|0-119|1-12|1-31|  
||(1980에 상대적)|||  
  
## <a name="see-also"></a>참고 항목  
 [전역 상수](../c-runtime-library/global-constants.md)
