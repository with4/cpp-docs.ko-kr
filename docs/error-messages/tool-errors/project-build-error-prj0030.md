---
title: 프로젝트 빌드 오류 PRJ0030 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0030
dev_langs:
- C++
helpviewer_keywords:
- PRJ0030
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1bf1c9137f8c4ed0d80955eef38b07ea86204a5c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33317660"
---
# <a name="project-build-error-prj0030"></a>프로젝트 빌드 오류 PRJ0030
매크로 확장 오류입니다. $(매크로)에 대해 수준 32를 넘는 재귀 호출을 실행 합니다.  
  
 이 오류는 재귀 매크로에 의해 발생 합니다. 예를 들어, 설정 하는 경우는 **중간 디렉터리** 속성 (참조 [일반 속성 페이지 (프로젝트)](../../ide/general-property-page-project.md)) $ (IntDir), 재귀 해야 합니다.  
  
 이 오류를 해결 하려면 매크로 또는 속성을 정의 하는 데 사용 되는 매크로 기준으로 정의 하지 않습니다.