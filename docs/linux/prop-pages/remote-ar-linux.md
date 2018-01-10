---
title: "원격 아카이브 속성(C++ Linux) | Microsoft Docs"
ms.custom: 
ms.date: 9/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ee1e44c-8337-4c3a-b2f3-35e4be954f9f
author: mikeblome
ms.author: mblome
manager: ghogen
f1_keywords:
- VC.Project.Ar.CreateIndex
- VC.Project.Ar.CreateThinArchive
- VC.Project.Ar.NoWarnOnCreate
- VC.Project.Ar.TruncateTimestamp
- VC.Project.Ar.SuppressStartupBanner
- VC.Project.Ar.Verbose
- vc.project.AdditionalOptionsPage
- VC.Project.Ar.OutputFile
- VC.Project.VCConfiguration.BuildLogFile
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 83b69c8aea824f08f3db6aa5f5b7bf01cacb339e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="remote-archive-properties-c-linux"></a>원격 아카이브 속성(C++ Linux)

속성 | 설명
--- | ---
아카이브 인덱스 만들기 | 아카이브 인덱스(ranlib 참조)를 만듭니다.  이를 통해 자체 소유 라이브러리 내에서 종속성 링크 및 축소를 빠르게 할 수 있습니다.
Thin 아카이브 만들기 | Thin 아카이브를 만듭니다.  Thin 아카이브는 개체를 포함하는 대신 개체에 대한 상대 경로를 포함합니다.  Thin과 Normal 간에 전환하려면 기존의 라이브러리를 삭제해야 합니다.
만들기에 대한 경고 없음 | 라이브러리가 만들어질 때 경고를 표시하지 않습니다.
타임스탬프 자르기 | 타임스탬프 및 uids/gids에 0을 사용합니다.
시작 배너 표시 안 함 | 버전 번호를 표시하지 않습니다.
자세히 | 자세히
추가 옵션 | 추가 옵션입니다.
출력 파일 | /OUT 옵션은 lib가 만드는 프로그램의 기본 이름 및 위치를 재정의합니다.
보관 | 원격 시스템에서 정적 개체를 링크하는 동안 호출할 프로그램 또는 보관 경로를 지정합니다.
보관 시간 제한 | 원격 보관 시간 제한(밀리초)입니다.
출력 복사 | 원격 시스템에서 로컬 컴퓨터로 빌드 출력 파일을 복사할지 여부를 지정합니다.
