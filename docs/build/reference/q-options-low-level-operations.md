---
title: -Q 옵션 (하위 수준 작업) | Microsoft Docs
ms.custom: ''
ms.date: 1/23/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /q
dev_langs:
- C++
helpviewer_keywords:
- Q compiler option [C++]
- -Q compiler option [C++]
- /Q compiler option [C++]
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c8a18c5d790cf21e8eb130a2b2baa152e20d79a1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375037"
---
# <a name="q-options-low-level-operations"></a>/Q 옵션(하위 수준 작업)

사용할 수는 **/Q** 컴파일러 옵션 다음 하위 수준의 컴파일러 작업을 수행 합니다.

- [/Qfast_transcendentals (빠른 초월수 강제)](../../build/reference/qfast-transcendentals-force-fast-transcendentals.md): 빠른 초월수를 생성 합니다.

- [/Qifist (_ftol 표시 안 함)](../../build/reference/qifist-suppress-ftol.md): 억제 `_ftol` 정수 형식으로 부동 소수점 형식에서 변환 필요 (x86 전용)를가 하는 경우.

- [/Qimprecise_fwaits (Try 블록 내의 fwait 제거)](../../build/reference/qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): 제거 `fwait` 내 명령 `try` 블록입니다.

- [/Qpar (자동 평행 화)](../../build/reference/qpar-auto-parallelizer.md):으로 표시 된 루프의 자동 병렬화를 사용 하면는 [#pragma loop ()](../../preprocessor/loop.md) 지시문입니다.

- [/ /Qpar-report (자동 평행 화 도우미 보고 수준)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md): 자동 병렬화에 대 한 수준을 보고 사용 하도록 설정 합니다.

- [/Qsafe_fp_loads](../../build/reference/qsafe-fp-loads.md): 부동 소수점 레지스터 로드 하 고 메모리 및 MMX 사이의 이동에 대 한 등록에 대 한 최적화가 억제 됩니다.

- [/ Qspectre](../../build/reference/qspectre.md): 특정 유령 보안 취약점을 완화 하는 명령을 생성 합니다.

- [/Qvec-report (자동 벡터화 도우미 보고 수준)](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md): 자동 벡터화에 대 한 수준을 보고 사용 하도록 설정 합니다.

## <a name="see-also"></a>참고자료

[컴파일러 옵션](../../build/reference/compiler-options.md)  
[컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)  
