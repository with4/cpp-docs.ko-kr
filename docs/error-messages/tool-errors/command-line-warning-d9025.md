---
title: "명령줄 경고 D9025 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- D9025
dev_langs:
- C++
helpviewer_keywords:
- D9025
ms.assetid: 6edff72c-1508-46c2-99f4-0e4b3c5e60c9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d95c4c16b472f0e1b37a981df7f73ff573d06447
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="command-line-warning-d9025"></a>명령줄 경고 D9025
옵션 '2'와 ' option1' 재정의  
  
 *option1* 옵션 지정 되었지만 하 여 다음 재정의 된 *옵션 2*합니다. *옵션 2* 옵션 사용 되었습니다.  
  
 모순 또는 호환 되지 않는 지시문을 지정 하는 두 가지 옵션이 명령줄에서 오른쪽에 있는 옵션에 지정 되었거나 암시 지시문 사용 됩니다.  
  
 개발 환경에서 컴파일하는 경우이 경고가 발생 하 고 확실 하지 않은 충돌 하는 옵션에서 생성 되는 위치는 다음을 고려 합니다.  
  
-   코드 또는 프로젝트의 프로젝트 설정에서 옵션을 지정할 수 있습니다. 컴파일러의 조합은 [명령줄 속성 페이지](../../ide/command-line-property-pages.md) 에서 충돌 하는 옵션을 표시 하 고는 **모든 옵션** 옵션, 그렇지 않으면 프로젝트의 속성 페이지에 옵션이 설정 되어 다음 필드 소스 코드에서 설정 됩니다.  
  
     프로젝트의 속성 페이지에 옵션이 설정 되어, 하는 경우 (솔루션 탐색기에서 선택한 프로젝트 노드)와 컴파일러의 전처리기 속성 페이지를 찾습니다.  여기서 설정, 솔루션 탐색기에서 각 소스 코드 파일에 대 한 전처리기 속성 페이지 설정이 있는지 확인 하는 옵션을 표시 되지 않으면 있습니다 추가 되지 않습니다.  
  
     코드에서 옵션이 설정 되어 코드 또는 windows 헤더에서 설정할 수 없습니다.  전처리 파일을 만들어 볼 수 있습니다 ([/P](../../build/reference/p-preprocess-to-a-file.md)) 기호를 검색 하 고 있습니다.