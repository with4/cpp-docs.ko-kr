---
title: "프로젝트 빌드 경고 PRJ0041 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PRJ0041
dev_langs: C++
helpviewer_keywords: PRJ0041
ms.assetid: dc9f4cf9-6bd5-4222-89e8-7802a59bb96b
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e5a9d5fb5350e4ae6b33fc167aae14b1361291e9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="project-build-warning-prj0041"></a>프로젝트 빌드 경고 PRJ0041
찾을 수 없습니다 '종속성' 'file' 파일에 대 한 종속성입니다. 프로젝트가 빌드할 수 있지만이 파일을 찾을 때까지 최신 표시 계속 될 수 있습니다.  
  
 파일 (리소스 파일 또는.idl/.odl 파일 예를 들어 포함 된 include 문이 프로젝트 시스템에서 확인할 수 없습니다.  
  
 프로젝트 시스템에서 전처리기 문 (예: #if)를 처리 하지 않으므로 잘못 된 문이 실제로으로 빌드의 일부로 포함 되지 않을 수 있습니다.  
  
 이 경고를 해결 하려면.rc 파일에서 불필요 한 모든 코드를 삭제 하거나 적절 한 이름의 자리 표시자 파일을 추가 합니다.