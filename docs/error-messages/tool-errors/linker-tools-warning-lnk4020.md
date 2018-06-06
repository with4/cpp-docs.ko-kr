---
title: 링커 도구 경고 LNK4020 | Microsoft Docs
ms.custom: ''
ms.date: 05/29/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4020
dev_langs:
- C++
helpviewer_keywords:
- LNK4020
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e55239b90910f6c151949c53939d4f8ed7c15c5
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34570695"
---
# <a name="linker-tools-warning-lnk4020"></a>링커 도구 경고 LNK4020

> 형식 레코드가 '*filename*' 손상 되었습니다; 일부 기호와 형식 디버거에서 액세스할 수 있습니다

PDB 파일 *filename* 손상 된 형식 레코드를 포함 합니다.

이 문제는 주로 다른 빌드 문제;에 대 한 보조 다른 오류 및 경고를 처리 하는 첫 번째 보고 된 빌드 문제를 하지 않은 첫 번째입니다. 첫 번째 보고 된 문제 라면 빌드 디렉터리를 정리 하 여 프로젝트를 다시 작성 해야 합니다. 병렬 빌드 프로세스를 사용 하는 경우 빌드를 serialize 할 때 오류가 계속 발생 하는 경우 참조 하십시오.