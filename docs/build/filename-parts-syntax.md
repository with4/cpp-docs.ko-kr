---
title: "파일 이름 부분 구문 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- syntax, filename-parts
- filename-parts syntax in NMAKE
- NMAKE program, syntax
ms.assetid: 48fe38e0-3f3b-40e6-894c-330ee775a656
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: be9a3cf9c91fecedd596ae7db74158f376ffc00c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="filename-parts-syntax"></a>파일 이름 부분 구문
명령에서 파일 이름 부분 구문 (수도 있음 묵시적된 종속) 하면 첫 번째 종속 파일의 구성 요소를 나타냅니다. 파일 이름 구성 요소입니다 파일의 드라이브, 경로, 기본 이름 및 지정 된 대로 확장 하지 디스크에 있습니다. 사용 하 여 **%s** 전체 파일 이름을 나타내는입니다. 사용 하 여 **% &#124;** [*부분*]**F** (세로 막대 백분율 기호 뒤에 문자가), 파일 이름 부분을 나타내는를 여기서 *부분* 0 개 이상의 다음 문자 수 순서에 관계 없이 합니다.  
  
|글자|설명|  
|------------|-----------------|  
|문자 없음|전체 이름 (동일 **%s**)|  
|**d**|드라이브|  
|**p**|Path|  
|**f**|파일 기본 이름|  
|**e**|파일 확장명|  
  
 예를 들어 파일 c:\prog.exe입니다.  
  
-   %s c:\prog.exe 됩니다.  
  
-   % &#124; F c:\prog.exe 됩니다.  
  
-   % &#124; dF는 c 됩니다  
  
-   % &#124; pF는 c:\ 됩니다  
  
-   % &#124; fF는 prog 됩니다  
  
-   % &#124; eF는 exe 됩니다  
  
## <a name="see-also"></a>참고 항목  
 [메이크파일의 명령](../build/commands-in-a-makefile.md)