---
title: 2.4 작업 공유 구문 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 25bb4ded-8466-4daa-a863-766b5a99b995
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c00eb94055f26954a283a6172f69228804832ac4
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33689638"
---
# <a name="24-work-sharing-constructs"></a>2.4 작업 공유 구문
작업 공유 생성자 배포 발생 하는 팀의 멤버 간에 연결 된 문 실행 합니다. 작업 공유 지시문은 새 스레드를 시작 하지 않으며 없습니다 묵시적된 장벽 작업 공유 구문에 대 한 항목에.  
  
 작업 공유의 시퀀스를 생성 하 고 **장벽** 발생 지시문 팀의 모든 스레드에 대해 동일 해야 합니다.  
  
 다음 섹션에 설명 되어 및 OpenMP 다음과 같은 작업 공유 생성자를 정의 합니다.  
  
-   **에 대 한** 지시문  
  
-   **섹션** 지시문  
  
-   **단일** 지시문