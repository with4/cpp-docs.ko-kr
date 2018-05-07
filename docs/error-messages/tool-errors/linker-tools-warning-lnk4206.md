---
title: 링커 도구 경고 LNK4206 | Microsoft Docs
ms.date: 12/05/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4206
dev_langs:
- C++
helpviewer_keywords:
- LNK4206
ms.assetid: 6c108e33-00cf-4c5a-830d-d65d470930a7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f0cb74776f307affb0455d972e27e594e6d06294
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4206"></a>링커 도구 경고 LNK4206

> 미리 컴파일된 형식 정보를 찾을 수 없습니다. '*filename*' 링크 되지 않았거나 덮어쓴; 디버그 정보가 없는 것 처럼 개체를 링크 합니다.

*filename* 개체 파일을 사용 하 여 컴파일된 [/Yc](../../build/reference/yc-create-precompiled-header-file.md), LINK 명령에 지정 되지 않았거나 덮어 쓰여졌습니다.

이 경고에 대 한 일반적인 시나리오에는 라이브러리에는 /Yc로 컴파일된.obj 및.obj 사용자 코드에서 기호 참조가 많이 있는입니다.  이 경우 링커는 또는 사용 하지 (그 역시 볼).obj 파일입니다.  이 경우 코드를 다시 컴파일하거나 하 고 사용 해야 [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) 사용 하 여 컴파일된 개체에 대 한 [/Yu](../../build/reference/yu-use-precompiled-header-file.md)합니다.