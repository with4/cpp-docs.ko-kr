---
title: 프로젝트 빌드 오류 PRJ0032 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0032
dev_langs:
- C++
helpviewer_keywords:
- PRJ0032
ms.assetid: bc6acbea-4041-4237-8b5a-f0434705d89f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d6be9a343ae9d9ce1e3d862cc0a397f1d61ccdea
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="project-build-error-prj0032"></a>프로젝트 빌드 오류 PRJ0032
프로젝트 수준의 사용자 지정 빌드 단계에 대 한 '출력' 속성이 '매크로' out 'macro_expansion' 계산 되는 포함 되어 있습니다.  
  
 프로젝트에서 사용자 지정 빌드 단계에는 매크로 확인 문제 때문 출력이 잘못 되었습니다. 이 오류는 경로가 잘못 되었습니다, 문자 또는 파일 경로에서 허용 하지 않는 문자 조합을 포함 된 의미할 수도 있습니다.  
  
 이 오류를 해결 하려면 매크로 수정 하거나 경로 지정을 수정 합니다. 확인 된 경로 프로젝트 디렉터리에서 절대 경로입니다.