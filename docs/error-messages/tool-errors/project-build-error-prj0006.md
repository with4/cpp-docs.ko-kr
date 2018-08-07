---
title: 프로젝트 빌드 오류 PRJ0006 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0006
dev_langs:
- C++
helpviewer_keywords:
- PRJ0006
ms.assetid: ce092be4-1652-414f-8cb5-b97ef5841f89
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 151c22bf13c13de21e89a5c96185cf1c4c1ca349
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33317481"
---
# <a name="project-build-error-prj0006"></a>프로젝트 빌드 오류 PRJ0006
'File' 임시 파일을 열 수 없습니다. 파일이 있는지, 그리고 디렉터리 쓰기 금지 되어 있는지 확인 합니다.  
  
 Visual c + + 빌드 프로세스 중에 임시 파일을 만들 수 없습니다. 원인은 다음과이 같습니다.  
  
-   임시 디렉터리가 없습니다.  
  
-   임시 디렉터리 읽기 전용입니다.  
  
-   디스크 공간이 부족 합니다.  
  
-   $ (Intdir) 폴더는 읽기 전용 이거나 임시 파일은 읽기 전용을 포함 합니다.  
  
 이 오류는 다음 오류 PRJ0007도 발생할: 출력 디렉터리 '디렉터리'를 만들 수 없습니다. 오류 PRJ0007 $ (intdir) 디렉터리를 만들 수 없습니다, 일시적으로 파일의 생성을 암시도 실패를 의미 합니다.  
  
 임시 파일을 지정할 때마다 생성 됩니다.  
  
-   응답 파일입니다.  
  
-   사용자 지정 빌드 단계입니다.  
  
-   빌드 이벤트입니다.