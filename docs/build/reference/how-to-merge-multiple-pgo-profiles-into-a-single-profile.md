---
title: '방법: 여러 개의 PGO 프로필을 단일 프로필로 병합 | Microsoft Docs'
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- merging profiles
- profile-guided optimizations, merging profiles
ms.assetid: aab686b5-59dd-40d1-a04b-5064690f65a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ca8fd6ef94af290d568f3186747c659b918c0fd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372284"
---
# <a name="how-to-merge-multiple-pgo-profiles-into-a-single-profile"></a>방법: 여러 개의 PGO 프로필을 단일 프로필로 병합

프로필 기반 최적화 (PGO)는 프로 파일링 시나리오에 따라 최적화 된 이진 파일을 만드는 데 유용한 도구입니다. 하지만 몇 가지 중요 한, 아직 고유 시나리오는 응용 프로그램을 훨씬 쉽게? 다양 한 시나리오에서 PGO 사용할 수 있는 단일 프로필로 만들려면 어떻게 해야 하면? Visual studio에서는 PGO 관리자 [pgomgr.exe](pgomgr.md),에서는이 작업을 수행 합니다.

프로필 병합에 대 한 구문은 다음과 같습니다.

`pgomgr /merge[:num] [.pgc_files] .pgd_files`

여기서 `num` 은이 병합에서 추가한.pgc 파일에 사용 하는 선택적 가중치입니다. 가중치는 다른 항목 보다 더 중요 한 몇 가지 시나리오 또는 시나리오를 여러 번 실행 하려는 경우에 주로 사용 됩니다.

> [!NOTE]
> PGO 관리자는 오래 된 프로필 데이터와 함께 작동 하지 않습니다. .Pgc 파일.pgd 파일을 병합 하려면.pgc 파일.pgd 파일을 생성 하는 동일한 링크 호출에 의해 생성 된 실행 개체에 의해 생성 되어야 합니다.

## <a name="examples"></a>예제

PGO 관리자는이 예제에서는 6 번 pgdFile.pgd에 pgcFile.pgc 추가합니다.

`pgomgr /merge:6 pgcFile.pgc pgdFile.pgd`

이 예제에서는 PGO 관리자 pgcFile1.pgc 및 pgcFile2.pgc 각.pgc 파일에 대해 두 번 pgdFile.pgd를에 추가 합니다.

`pgomgr /merge:2 pgcFile1.pgc pgcFile2.pgc pgdFile.pgd`

.Pgc 파일 인수 없이 PGO 관리자를 실행 하는 경우 다음에 느낌표 (!)와 하나 이상의 다음 임의의 문자.pgd 파일로 동일한 기본 이름을 가진 모든.pgc 파일에 대 한 로컬 디렉터리를 검색 합니다. 예를 들어, 로컬 디렉터리에 파일 test.pgd, test!1.pgc, test2.pgc, 및 test!hello.pgc, 다음 명령은 로컬 디렉터리에서 실행 될 경우 **pgomgr** test.pgd test!1.pgc 및 test!hello.pgc 병합 합니다.

`pgomgr /merge test.pgd`

## <a name="see-also"></a>참고자료

[프로필 기반 최적화](../../build/reference/profile-guided-optimizations.md)
