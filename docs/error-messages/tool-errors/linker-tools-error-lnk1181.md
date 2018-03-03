---
title: "링커 도구 오류 LNK1181 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1181
dev_langs:
- C++
helpviewer_keywords:
- LNK1181
ms.assetid: 984b0db6-e331-4284-b2a7-a212fe96c486
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8f5092d4f3ce7b4f96ca4dc5c1554483a7fc3a0b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1181"></a>링커 도구 오류 LNK1181
입력된 '한 filename' 파일을 열 수 없습니다.  
  
 링커 찾을 수 없습니다 `filename` 존재 하지 않는 않거나 경로 찾을 수 없습니다.  
  
 오류 LNK1181 포함에 대 한 몇 가지 일반적인 원인은:  
  
-   `filename`참조를 추가 종속성 링커 줄 하지만 파일에 존재 하지 않습니다.  
  
-   A **/LIBPATH** 포함 된 디렉터리를 지정 하는 문을 `filename` 없습니다.  
  
 위 문제를 해결 하려면 링커 줄에서 참조 되는 모든 파일 시스템에 있는지 확인 합니다.  또한 있는지를 확인 한 **/LIBPATH** 링커 종속 파일을 포함 하는 각 디렉터리에 대 한 문입니다.  
  
 또 다른 가능한 원인은 lnk1181 공백이 포함된 된 긴 파일 이름을 따옴표로 묶인 되지 것입니다.  이 경우 링커는만 첫 번째 공백 까지의 파일 이름으로 인식 한 다음 파일 확장명이. obj.  이 상황을 해결 방법은 묶습니다 긴 파일 이름 (경로 및 파일 이름) 인용 부호로 합니다.  
  
 자세한 내용은 참조 [링커 입력으로 사용 하는.lib 파일](../../build/reference/dot-lib-files-as-linker-input.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [/LIBPATH (추가 Libpath)](../../build/reference/libpath-additional-libpath.md)