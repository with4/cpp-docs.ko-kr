---
title: 사용자 지정 빌드 단계 또는 빌드 이벤트의 출력 서식 지정 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- builds [C++], build events
- custom build steps [C++], output format
- events [C++], build
- build events [C++], output format
- build steps [C++], output format
- builds [C++], custom build steps
ms.assetid: 92ad3e38-24d7-4b89-90e6-5a16f5f998da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7da71e6391d2d3223b47ba528686d2fec003ab3a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="formatting-the-output-of-a-custom-build-step-or-build-event"></a>사용자 지정 빌드 단계 또는 빌드 이벤트의 출력 형식 지정
사용자 지정 빌드 단계 또는 빌드 이벤트의 출력 형식이 올바른지, 사용자는 다음과 같은 이점을 메시지가 나타납니다.  
  
-   경고 및 오류에서 계산 되는 **출력** 창.  
  
-   출력에 표시 된 **작업 목록** 창.  
  
-   출력을 클릭 하면는 **출력** 창에 해당 항목이 표시 됩니다.  
  
-   F1 작업에서 사용 되는 **작업 목록** 창 또는 **출력** 창.  
  
 출력의 형식은 같아야 합니다.  
  
 {*filename* (*line #* [, *열 #*]) &#124; *toolname*} **:**  
  
 [*텍스트*] {**오류** &#124; **경고**} *코드 # # #***:*** 지역화 가능한 문자열*  
  
 [ *텍스트* ]  
  
 여기서  
  
-   {*는* &#124; *b*}는 하나의 선택 *는* 또는 *b*합니다.  
  
-   [`ccc`] 매개 변수 또는 선택적 문자열입니다.  
  
 예를 들어:  
  
 C:\\*sourcefile.cpp*(134): 오류 C2143: 구문 오류: 없습니다. ';' 하기 전에 '을 (를) '  
  
 링크: 심각한 오류 LNK1104: 파일을 열 수 없습니다 '*somelib.lib*'  
  
## <a name="see-also"></a>참고 항목  
 [사용자 지정 빌드 단계 및 빌드 이벤트 이해](../ide/understanding-custom-build-steps-and-build-events.md)