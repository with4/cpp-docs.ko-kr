---
title: "프로젝트 빌드 오류 PRJ0024 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- PRJ0024
dev_langs:
- C++
helpviewer_keywords:
- PRJ0024
ms.assetid: 8bde6368-6c1b-4e04-bc5e-3c6d0b8fa1d7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2cf9ad974856f132599932a32b954e50453adf56
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0024"></a>프로젝트 빌드 오류 PRJ0024
'Path' 유니코드 경로 사용자의 ANSI 코드 페이지로 변환 하지 못했습니다.  
  
 ***경로*** 는 경로 문자열의 원래 유니코드 버전입니다. 경우에이 오류가 발생할 수는 현재 시스템 코드 페이지에 대 한 ANSI로 직접 변환할 수 없는 유니코드 경로가 있을 합니다.  
  
 이 오류는 컴퓨터에 있는 코드 페이지를 사용 하는 시스템에서 개발 된 프로젝트와 작업 하는 경우에 발생할 수 있습니다.  
  
 이 오류에 대 한 확인을 ANSI 텍스트를 사용 하거나 코드 페이지를 컴퓨터에 설치 하 고 시스템 기본값으로 설정 하는 경로 업데이트 하기 위해서입니다.