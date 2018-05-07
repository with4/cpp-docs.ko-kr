---
title: BSCMAKE 오류 BK1509 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK1509
dev_langs:
- C++
helpviewer_keywords:
- BK1509
ms.assetid: 53df7037-1913-4b63-b425-c0bf44081792
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 825d1e1e119aa80445c5ae15804bbdde4a3d8bf9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="bscmake-error-bk1509"></a>BSCMAKE 오류 BK1509
힙 공간이 부족 합니다.  
  
 BSCMAKE 가상 메모리를 포함 하 여 메모리 부족 오류가 발생 했습니다.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>아래의 해결 방법 따라 수정합니다.  
  
1.  디스크 공간을 확보 합니다.  
  
2.  스왑 파일의 크기를 늘립니다.  
  
3.  Windows 스왑 파일의 크기를 늘립니다.  
  
4.  BSCMAKE /Ei를 사용 하 여 필요한 메모리를 줄이거나 /Es 일부를 제거 하려면 입력 파일이 나 /Em으로 매크로 본문을 제거 합니다.