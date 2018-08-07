---
title: 프로젝트 빌드 오류 PRJ0034 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0034
dev_langs:
- C++
helpviewer_keywords:
- PRJ0034
ms.assetid: 1da4a55b-231b-4476-8545-6997628fbc00
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a65ca2c53ba2801f861471c66f7e1f2ec8766345
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33319080"
---
# <a name="project-build-error-prj0034"></a>프로젝트 빌드 오류 PRJ0034
프로젝트 수준의 사용자 지정에 대 한 ' 추가 종속성 ' 속성이 'macro_expansion'으로 계산 되는 포함 된 단계 '매크로를' 빌드합니다.  
  
 프로젝트에서 사용자 지정 빌드 단계에는 추가 종속성 매크로 확인 문제 때문에 오류가 있습니다. 이 오류는 경로가 잘못 되었습니다, 문자 또는 파일 경로에서 허용 하지 않는 문자 조합을 포함 된 의미할 수도 있습니다.  
  
 이 오류를 해결 하려면 매크로 수정 하거나 경로 지정을 수정 합니다. 확인 된 경로 프로젝트 디렉터리에서 절대 경로입니다.