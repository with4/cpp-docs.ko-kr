---
title: "인라인 파일 텍스트 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- inline files, creating text
- NMAKE program, inline files
- text, inline file
ms.assetid: b8a332ed-8244-4ff8-89e6-029d7f659725
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dcc27a303e9d03d2e899a76703bcfae5abfd0c04
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-inline-file-text"></a>인라인 파일 텍스트 만들기
인라인 파일은 임시 또는 영구입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      inlinetext  
.  
.  
.  
<<[KEEP | NOKEEP]  
```  
  
## <a name="remarks"></a>설명  
 지정 *inlinetext* 명령 실행 후 첫 번째 줄에 있습니다. 개별 줄의 시작 부분에 이중 꺾쇠괄호(<<)를 사용해서 끝을 표시합니다. 파일에 포함 되어 모든 *inlinetext* 구분 대괄호 앞입니다. *inlinetext* 매크로 확장이 및 대체 있지만 지시문 또는 메이크파일 주석은 가질 수 있습니다. 공백, 탭 및 줄 바꿈 문자는 문자 그대로 처리 됩니다.  
  
 임시 파일 세션의 기간에 존재 하 고 다른 명령을 사용 하 여 다시 사용할 수 있습니다. 지정 **유지** NMAKE 세션; 후 파일을 유지 하려면 꺾쇠 괄호를 닫은 후 명명 되지 않은 파일은 생성 된 파일 이름으로 디스크에 보존 됩니다. 지정 **NOKEEP** 또는 임시 파일에 아무것도 표시 되지 않음. **유지** 및 **NOKEEP** 대/소문자 구분 없는 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [메이크파일의 인라인 파일](../build/inline-files-in-a-makefile.md)