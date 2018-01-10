---
title: "인라인 파일 지정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, inline files
- inline files [C++], specifying NMAKE
- files [C++], inline
ms.assetid: 393eccfb-3fc9-4bac-a30c-8ac8d221cca3
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ef2183390b2aca2fb54e1468bd59e697374a355a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="specifying-an-inline-file"></a>인라인 파일 지정
두 개의 꺾쇠 괄호를 지정 (<<) 명령에 여기서 *filename* 표시 하는 것입니다. 꺾쇠 괄호 매크로 확장 될 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
<<[filename]  
```  
  
## <a name="remarks"></a>설명  
 명령이 실행 되는 꺾쇠 괄호 바뀝니다 *filename*, 지정 하거나, 고유한 NMAKE에서 생성 된 이름으로 합니다. 를 지정 하는 경우 *filename* 공백이 나 탭 없이 꺾쇠 괄호 뒤와 야 합니다. 경로 사용할 수 있습니다. 확장명이 없는 필요 하거나 가정 합니다. 경우 *filename* 지정 파일이 현재에서 만들어집니다 하지 않거나 해당 이름의 파일 가기를; 그러지 않으면 TMP 디렉터리에 생성이 지정 된 디렉터리 (또는 현재 디렉터리 경우 TMP 환경 변수 정의 되지 않습니다). 이전 하는 경우 *filename* 는 계속 사용 NMAKE 이전 파일을 대체 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [메이크파일의 인라인 파일](../build/inline-files-in-a-makefile.md)