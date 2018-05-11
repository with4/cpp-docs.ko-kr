---
title: 기호 이름 제한 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.restrictions.name
dev_langs:
- C++
helpviewer_keywords:
- symbol names
- symbols, names
- restrictions, symbol names
ms.assetid: 4ae7f695-ca86-4f4b-989a-fe6f89650ff7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 59ee6ce257609c4761e43630a66de9cb9b996269
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="symbol-name-restrictions"></a>기호 이름 제한
기호 이름에 대한 제한은 다음과 같습니다.  
  
-   모든 [기호](../windows/symbols-resource-identifiers.md) 응용 프로그램의 범위 내에서 고유 해야 합니다. 이렇게 하면 헤더 파일에서 기호 정의 충돌을 방지할 수 있습니다.  
  
-   기호 이름에 유효한 문자는 A-Z, a-z, 0-9 및 밑줄(_)입니다.  
  
-   기호 이름은 숫자로 시작할 수 없으며 247자로 제한됩니다.  
  
-   기호 이름에는 공백을 사용할 수 없습니다.  
  
-   기호 이름은 대/소문자를 구분하지 않지만 첫 번째 기호 정의의 대/소문자는 유지됩니다. 기호를 정의하는 헤더 파일은 리소스 컴파일러/편집기 및 C++ 프로그램에서 리소스 파일에 정의된 리소스를 참조하는 데 사용됩니다. 대/소문자만 다른 두 기호 이름에 대해 C++ 프로그램은 별도의 두 기호로 보지만 리소스 컴파일러/편집기는 두 이름이 하나의 단일 기호를 나타내는 것으로 봅니다.  
  
    > [!NOTE]
    >  아래에 간략하게 설명된 표준 기호 이름 체계(ID*_[keyword])를 따르지 않고 기호 이름이 리소스 스크립트 컴파일러에 알려진 키워드와 동일한 경우 리소스 스크립트 파일을 빌드하려고 하면 진단하기 어려운 임의 오류가 생성될 수 있습니다. 이를 방지하려면 표준 이름 지정 체계를 준수하세요.  
  
 기호 이름에는 해당 이름이 나타내는 리소스 또는 개체의 종류를 나타내는 설명 접두사가 있습니다. 이러한 설명 접두사는 텍스트 조합 ID로 시작합니다. MFC(Microsoft Foundation Class) 라이브러리는 다음 표에 표시된 기호 명명 규칙을 사용합니다.  
  
|범주|접두사|사용|  
|--------------|------------|---------|  
|자료|IDR_ IDD_ IDC_ IDI_ IDB_|액셀러레이터 키 또는 메뉴(및 연결된 리소스 또는 사용자 지정 리소스) 대화 상자 커서 아이콘 비트맵|  
|메뉴 항목|ID_|Menu item|  
|명령|ID_|명령|  
|컨트롤 및 자식 창|IDC_|Control|  
|문자열|IDS_|문자열 테이블의 문자열|  
|MFC|AFX_|미리 정의된 MFC 기호에 예약됨|  
  

  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [기호 또는 기호 이름 (ID) 변경](../windows/changing-a-symbol-or-symbol-name-id.md)   
 [기호 값 제한](../windows/symbol-value-restrictions.md)   
 [미리 정의된 기호 ID](../windows/predefined-symbol-ids.md)