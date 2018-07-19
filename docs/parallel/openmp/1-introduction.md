---
title: 1. 소개 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c42e72bc-0e31-4b1c-b670-cd82673c0c5a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 883af9cb48a0fb13dbb9a758d6f8174096d4c0c3
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33685842"
---
# <a name="1-introduction"></a>1. 소개
이 문서는 컴파일러 지시문, 라이브러리 함수 및 C 및 c + + 프로그램에서 공유 메모리 병렬 처리를 지정 하는 데 사용할 수 있는 환경 변수 컬렉션을 지정 합니다. 이 문서에서 설명 하는 기능으로 통칭 되는 *OpenMP C/c + + 응용 프로그램 인터페이스 (API)* 합니다. 이 사양의 목표는 병렬 프로그래밍에 대 한 모델을 제공 하는 프로그램 여러 공급 업체의 공유 메모리 아키텍처 간에 이식이 가능한 것으로 수 있습니다. OpenMP C/c + + API 한 공급 업체에서 컴파일러에서 지원 됩니다. OpenMP에 대 한 자세한 내용은 포함 하는 *OpenMP 포트란 응용 프로그램 인터페이스*, 다음 웹 사이트에서 찾을 수 있습니다.  
  
 [http://www.openmp.org](http://www.openmp.org)  
  
 지시문, 라이브러리 함수 및이 문서에 정의 된 환경 변수는 만들고 이식성을 허용 하는 동안 병렬 프로그램을 관리 하는 사용자를 수 있습니다. 지시문은 C를 확장 하 고 여러 데이터 (SPMD) 구문, 작업 공유 구문 및 동기화 구문 순차적 c + + 프로그래밍 모델입니다. 단일 프로그램 공유 및 화 데이터에 대 한 지원을 제공 합니다. OpenMP C 및 c + + API를 지 원하는 컴파일러에서 명령줄 옵션을 활성화 하 고 모든 OpenMP 컴파일러 지시문의 해석 허용 하는 컴파일러에 포함 됩니다.