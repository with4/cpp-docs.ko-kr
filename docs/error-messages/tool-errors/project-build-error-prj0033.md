---
title: "프로젝트 빌드 오류 PRJ0033 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- PRJ0033
dev_langs:
- C++
helpviewer_keywords:
- PRJ0033
ms.assetid: 84d4a052-0586-4b78-9315-81c1e8386c1e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0cd7bcc0239ce88a19ae6009195f120a88be59ad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0033"></a>프로젝트 빌드 오류 PRJ0033
사용자 지정 빌드에 대 한 ' 추가 종속성 ' 속성이 한 단계씩 코드 실행 매크로 대 한 파일에 포함 된 ' file' ' '로 확인 됨 'macro_expansion'.  
  
 파일에 사용자 지정 빌드 단계에는 추가 종속성 매크로 확인 문제 때문에 오류가 있습니다. 이 오류는 경로가 잘못 되었습니다, 문자 또는 파일 경로에서 허용 하지 않는 문자 조합을 포함 된 의미할 수도 있습니다.  
  
 이 오류를 해결 하려면 매크로 수정 하거나 경로 지정을 수정 합니다. 확인 된 경로 프로젝트 디렉터리에서 절대 경로입니다.