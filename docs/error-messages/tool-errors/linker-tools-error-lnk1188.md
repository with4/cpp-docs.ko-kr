---
title: 링커 도구 오류 LNK1188 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1188
dev_langs:
- C++
helpviewer_keywords:
- LNK1188
ms.assetid: 4af574b0-5b41-4580-9a37-52a634add995
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e31943ae253a332576fba73102db410b103a0096
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1188"></a>링커 도구 오류 LNK1188
잘못 된 fixup 대상 BADFIXUPSECTION:: 'symbol'; 가능한 길이 섹션이 0  
  
 VxD 링크 중에 재배치의 대상 섹션을 아닙니다. Link386 (이전 버전), 다른 길이가 0이 아닌 섹션 0 길이 섹션을 결합 하는 OMF 그룹 기록 (MASM 그룹 지시문에서 생성) 사용 합니다. GROUP 지시문 및 빈 섹션 COFF 형식은 지원 하지 않습니다. 링크 자동으로 해당이 유형의 OMF 개체 COFF로 변환 하는 경우이 오류가 발생할 수 있습니다.