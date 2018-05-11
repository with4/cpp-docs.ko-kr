---
title: 링커 도구 오류 LNK1309 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1309
dev_langs:
- C++
helpviewer_keywords:
- LNK1309
ms.assetid: 10146071-883f-4849-97d1-c7468f90efbb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f179a74823be1293bc927afe122c4bf14c0030b9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1309"></a>링커 도구 오류 LNK1309
type1 모듈이 발견 되었습니다. 잘못 된 스위치 /CLRIMAGETYPE:type2 핸들로  
  
 사용 하는 CLR 이미지를 요청 했지만 **/CLRIMAGETYPE** 하나 이상의 모듈이 해당 형식과 호환 되지 않으므로 링커가 해당 형식의 이미지 생성할 수 없습니다.  
  
 예를 들어 lnk1309 지정 하는 경우 **/clrimagetype: safe** 로 빌드된 모듈 전달 **/clr: pure**합니다.  
  
 부분적으로 신뢰할 수 있는 CLR 순수 응용 프로그램 [d] ptrustu.lib을 사용 하 여 빌드 하려는 경우에 LNK1309 나타납니다. 부분적으로 신뢰할 수 있는 응용 프로그램을 만드는 방법에 대 한 자세한 내용은 참조 하십시오. [하는 방법: CRT 라이브러리 DLL에는 부분적으로 신뢰할 수 있는 응용 프로그램 종속성을 제거 하 여 만들](../../dotnet/create-a-partially-trusted-application.md)합니다.  
  
 자세한 내용은 참조 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 및 [/CLRIMAGETYPE (지정 종류의 CLR 이미지)](../../build/reference/clrimagetype-specify-type-of-clr-image.md)합니다.