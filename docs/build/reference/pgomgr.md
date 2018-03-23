---
title: pgomgr | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- pgomgr program
- profile-guided optimizations, pgomgr
ms.assetid: 74589126-df18-42c9-8739-26d60e148d6a
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 743665bbe0ee9c3df08d197d203e95d08542f613
ms.sourcegitcommit: ee7d74683af7631441c8c7f65ef5ceceaee4a5ee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="pgomgr"></a>pgomgr

.Pgd 파일에 하나 이상의.pgc 파일에서 프로필 데이터를 추가합니다.

## <a name="syntax"></a>구문

> **pgomgr** [*options*] *pgcfiles* *pgdfile*

### <a name="parameters"></a>매개 변수

*options*<br/>
다음 옵션을 지정할 수 있습니다 **pgomgr**:

- **/help** 또는 **/?** 사용 가능한 표시 **pgomgr** 옵션입니다.

- **/clear** 하면.pgd 파일의 모든 프로필 정보가 지워집니다. .pgc를 지정할 수 없습니다 있을 때 파일 **/clear** 지정 됩니다.

- **/detail** 선형 그래프 진행 정보를 포함 하 여 자세한 통계를 표시 합니다.

- **요약/** 표시 기능별 통계.

- **고유한 /** 와 함께 사용할 경우 **요약/**, 원인 데코레이팅된 함수 이름을 표시 합니다. 기본값, **고유 /** 표시할 데코 레이트 되지 않은 함수 이름에는 사용 되지 않습니다.

- **병합/**[**: * * * n*] 하면 데이터가.pgc 파일이 나.pgd 파일에 추가할 파일입니다. 선택적 매개 변수 *n*, 데이터를 추가 해야 함을 지정할 수 있습니다 *n* 시간입니다. 예를 들어 시나리오의 경우는 일반적으로 완료 6 번 고객에 의해 이루어진다는 얼마나 자주 반영 하기 위해, 테스트 실행에서 두 번 수행 추가 하는 것으로 6 번.pgd 파일에 **pgomgr /merge:**합니다.

*pgcfiles*<br/>
하나 이상의.pgc 파일 프로필 데이터가.pgd 파일에 병합 합니다. 단일.pgc 파일이 나 여러.pgc 파일을 지정할 수 있습니다. .Pgc 파일을 지정 하지 않으면 **pgomgr** 해당 파일 이름이.pgd 파일로 같습니다 모든.pgc 파일을 병합 합니다.

*pgdfile* .pgd 파일을 병합 하는.pgc 파일 또는 파일의 데이터입니다.

## <a name="remarks"></a>설명

> [!NOTE]
> Visual Studio 개발자 명령 프롬프트 에서만에서이 도구를 시작할 수 있습니다. 시스템 명령 프롬프트 또는 파일 탐색기에서는 시작할 수 없습니다.

## <a name="example"></a>예제

이 예제 명령을 myapp.pgd 파일 한 프로필 데이터를 지웁니다.

`pgomgr /clear myapp.pgd`

이 예제에서는 명령은 프로필 데이터의에서 추가 myapp1.pgc.pgd 파일을 세 번:

`pgomgr /merge:3 myapp1.pgc myapp.pgd`

이 예제에서는 모든 myapp #.pgc 파일에서 프로필 데이터는 myapp.pgd 파일에 추가 됩니다.

`pgomgr -merge myapp1.pgd`

## <a name="see-also"></a>참고자료

[프로필 기반 최적화](profile-guided-optimizations.md)<br/>
[PgoAutoSweep](pgoautosweep.md)<br/>
[pgosweep](pgosweep.md)<br/>
