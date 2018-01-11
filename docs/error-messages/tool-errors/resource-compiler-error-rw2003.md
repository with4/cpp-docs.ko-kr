---
title: "리소스 컴파일러 오류 RW2003 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RW2003
dev_langs: C++
helpviewer_keywords: RW2003
ms.assetid: 9dc0ba70-6776-4aef-b316-5f1711d8e42e
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9f388ca21d95e7d675a6b9890a7368765b5c0d7e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-error-rw2003"></a>리소스 컴파일러 오류 RW2003
생성 오류  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면  
  
1.  **오류: 비트맵 리소스 파일에에서 없는 3.00 형식이**  
  
     Windows 버전 2.x 형식을 사용하는 비트맵은 버전 3.x 리소스 파일에서 사용할 수 없습니다. 비트맵 하거나 다시 그려야 3.x 형식으로 변환 해야 합니다.  
  
2.  **오류: 리소스 이름에 이전 dib가 있습니다. SDKPAINT를 통과**  
  
     DIB 장치 독립적 비트맵 () 지정된 된 리소스에서 Windows 3.0 형식을와 호환 되지 않습니다. 비트맵 하거나 다시 그려야 3.x 형식으로 변환 해야 합니다.  
  
3.  **오류: 리소스 파일 리소스 이름이 3.00 형식이 않습니다.**  
  
     아이콘 또는 커서 지정된 된 리소스의 이전 버전의 Windows에서 형식을 사용 했습니다. 아이콘 또는 커서를 다시 그리면 하거나 3.x 형식으로 변환 해야 합니다.  
  
4.  **알 수 없는 DIB 헤더 형식**  
  
     비트맵 헤더 BITMAPCOREHEADER 또는 BITMAPINFOHEADER 구조 않습니다.  
  
5.  **기호 정보를 초기화할 수 없습니다.**  
  
     이 오류는 Visual c + +에만 발생 합니다. 가능한 원인은 너무 많은 파일이 열려 있거나 열거나 Visual c + + 스크립트에서 기호를 가져오는 데 필요한 데이터 파일에 쓸 수 없기 때문입니다. Visual c + +로 지정 된 디렉터리에서 이러한 파일을 만들려고 시도 **TMP** 환경 변수 또는 지정 되지 않은 경우 현재 디렉터리입니다.  
  
6.  **기호 정보를 저장할 수 없습니다.**  
  
     이 오류는 Visual c + +에만 발생 합니다. 가능한 원인은 너무 많은 파일이 열려 있거나 닫거나 Visual c + + 스크립트에서 기호를 가져오는 데 필요한 데이터 파일에 쓸 수 없기 때문입니다. Visual c + +로 지정 된 디렉터리에서 이러한 파일을 사용 하려고 시도 **TMP** 환경 변수 또는 지정 되지 않은 경우 현재 디렉터리입니다.  
  
7.  **비트맵 파일 리소스 파일이 2.03 형식이 아닙니다.**  
  
     비트맵이 버전 2.03 이전의 형식을 사용했습니다. 버전 3.00 이상의 형식을 사용하여 비트맵을 변환하거나 다시 그려야 합니다.  
  
8.  **리소스가 너무 큽니다.**  
  
     Windows 3.1에 대 한 리소스는 대략 65000 바이트를 초과할 수 없습니다. 리소스를 않으면 다음 있습니다 됩니다 명령줄 리소스 컴파일러 또는 Visual c + +를 컴파일할 수 있습니다. 커서, 아이콘, 비트맵 또는 기타 파일 기반 리소스에는 이 제한이 적용되지 않습니다.  
  
9. **리소스 파일 3.00 형식이 아닙니다.**  
  
     커서 또는 아이콘을 이전 버전 3.00 형식을 사용 합니다. 리소스 변환 또는 형식을 사용 하 여 버전 3.00 다시 그려야 이상 이어야 합니다.  
  
10. **임시 파일을 열 수 없습니다.**  
  
     리소스 컴파일러/Visual C++에서 임시 파일을 열 수 없습니다. 가능한 원인은 디렉터리에 대 한 쓰기 권한을 않았는지 또는 디렉터리가 존재 하지 않습니다. 리소스 컴파일러/Visual C++는 **TMP** 환경 변수로 지정된 디렉터리 또는 지정되지 않은 경우 현재 디렉터리에서 이러한 파일을 사용하려고 합니다.