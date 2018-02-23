---
title: "사용자 지정 빌드 단계 속성(Linux C++) | Microsoft Docs"
ms.custom: 
ms.date: 10/17/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77a9c1fb-7c41-4a9b-9418-18ac17ce4e74
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: b46ee18fce79c0e1954d37a87f6380c73870fa12
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="custom-build-step-properties-linux-c"></a>사용자 지정 빌드 단계 속성(Linux C++)

속성 | 설명
--- | ---
명령줄 | 사용자 지정 빌드 단계에서 실행할 명령입니다.
설명 | 사용자 지정 빌드 단계를 실행할 때 표시되는 메시지입니다.
출력 | 사용자 지정 빌드 단계에서 생성되는 출력 파일입니다. 증분 빌드가 올바로 작동하려면 이 설정이 필요합니다.
추가 종속성 | 사용자 지정 빌드 단계에 사용할 추가 입력 파일의 세미콜론으로 구분한 목록입니다.
이후 실행 및 이전 실행 | 이러한 옵션은 나열된 대상 기준으로 빌드 프로세스에서 사용자 지정 빌드 단계가 실행되는 때를 정의합니다. 가장 일반적으로 나열되는 대상은 빌드 프로세스의 주요 단계를 나타내는 BuildGenerateSources, BuildCompile, BuildLink입니다. 종종 나열되는 다른 대상은 Midl, CLCompile, Link입니다.
출력을 콘텐츠로 처리 | 이 옵션은 .appx 패키지의 모든 콘텐츠 파일을 포함하는 Microsoft Store 또는 Windows Phone 앱에만 의미가 있습니다.