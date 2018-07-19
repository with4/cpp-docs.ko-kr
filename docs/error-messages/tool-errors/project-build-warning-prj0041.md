---
title: 프로젝트 빌드 경고 PRJ0041 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0041
dev_langs:
- C++
helpviewer_keywords:
- PRJ0041
ms.assetid: dc9f4cf9-6bd5-4222-89e8-7802a59bb96b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e845967b0a7116d6edade98b571de5bc1bcd9a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33318063"
---
# <a name="project-build-warning-prj0041"></a>프로젝트 빌드 경고 PRJ0041
찾을 수 없습니다 '종속성' 'file' 파일에 대 한 종속성입니다. 프로젝트가 빌드할 수 있지만이 파일을 찾을 때까지 최신 표시 계속 될 수 있습니다.  
  
 파일 (리소스 파일 또는.idl/.odl 파일 예를 들어 포함 된 include 문이 프로젝트 시스템에서 확인할 수 없습니다.  
  
 프로젝트 시스템에서 전처리기 문 (예: #if)를 처리 하지 않으므로 잘못 된 문이 실제로으로 빌드의 일부로 포함 되지 않을 수 있습니다.  
  
 이 경고를 해결 하려면.rc 파일에서 불필요 한 모든 코드를 삭제 하거나 적절 한 이름의 자리 표시자 파일을 추가 합니다.