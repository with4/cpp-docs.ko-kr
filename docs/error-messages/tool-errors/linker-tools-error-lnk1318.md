---
title: 링커 도구 오류 LNK1318 | Microsoft Docs
ms.custom: ''
ms.date: 05/29/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1318
dev_langs:
- C++
helpviewer_keywords:
- LNK1318
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 364c819c6ec2bf6e1195011eced6e6ad1699877b
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34570696"
---
# <a name="linker-tools-error-lnk1318"></a>링커 도구 오류 LNK1318

> 예기치 않은 PDB 오류입니다. *인해* '*세부 정보*'

링커 열기 읽거나 PDB 파일에 쓸 때 예기치 않은 오류가 발생 했습니다.

PDB 파일의 경우를 흔히 볼 문제에 대 한이 오류 메시지가 생성 됩니다. *인해* 및 *세부 정보* 오류가 발생 한 경우 링커로 제공 되는 정보를 나타냅니다. 이 PDB 파일을 다루기 많은 정보를 제공 하 고 별도 오류 메시지가 있을 때 일반적인 오류도 매우 유용 되지 않을 수 있습니다.

오류의 출처를 일반적인 없는 이므로 제네릭 조언을이 문제를 해결 하는 데 사용할 수 있는:

- 빌드 디렉터리에서 정리 작업을 수행 하 고 솔루션의 전체 빌드를 수행 합니다.

- 컴퓨터를 다시 부팅 또는 흩어진 되거나 응답이 없는 mspdbsrv.exe 프로세스 확인 하 고 작업 관리자의이 중지 합니다.

- 프로젝트 디렉터리에서 바이러스 백신 검사를 해제 합니다.

- 사용 하 여는 [/Zf](../../build/reference/zf.md) 컴파일러 옵션을 사용 하는 경우 [/MP](../../build/reference/mp-build-with-multiple-processes.md) MSBuild 또는 다른 병렬 빌드 프로세스입니다.

- 64 비트 호스트 된 도구 집합을 사용 하 여 빌드를 시도 하십시오.

- 필요한 경우 병렬 링크 문제를 완화 하기 위해 링크를 직렬화 합니다. Mspdbsrv.exe 링크의 한 인스턴스에서 시작 되 고 링크의 다른 인스턴스에 의해 이루어진다는 전에 종료 되는 경우이 오류가 발생할 수 있습니다 사용 합니다. 이 문제를이 수정 하는 경우 단점은 프로젝트 빌드를 완료 하려면 상당히 오래 걸릴 수 있습니다.