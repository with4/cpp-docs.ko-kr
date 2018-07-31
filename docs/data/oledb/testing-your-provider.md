---
title: 공급자 테스트 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- OLE DB providers, testing
ms.assetid: bf824fe4-81af-4ffb-beb3-4fa2928dc450
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 906156a24cfb58697ff4dd95e922f5ee326fd07d
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339730"
---
# <a name="testing-your-provider"></a>공급자 테스트
공급자를 해제 하기 전에 표시 된 순서에서 다음 테스트를 수행 해야 합니다. 이러한 테스트의 대부분의 사용자가 제대로 공급자 함수를 확인합니다.  
  
1.  테스트를 사용 하 여 공급자를 [소비자](../../data/oledb/creating-an-ole-db-consumer.md) OLE DB 소비자 템플릿을 사용 하 여 작성 된 응용 프로그램입니다. 테스트 소비자 공급자 (추가 또는 수정 하는 모든 코드)의 모든 기능 영역을 포함 해야 합니다.  
  
2.  ADO를 사용 하 여 작성 한 소비자 응용 프로그램을 사용 하 여 공급자를 테스트 합니다. 대부분의 개발자 (특히: Microsoft Visual Basic 및 Microsoft C# 개발자) 소비자 응용 프로그램에 대 한 ADO 또는 ADO.NET을 사용 합니다. 테스트 소비자는 공급자의 모든 기능 영역을 다루어야 합니다. ADO 소비자 응용 프로그램의 예제를 보려면 [Microsoft Visual Basic의 ADO 코드 예제](https://msdn.microsoft.com/library/ms807514.aspx)합니다.  
  
3.  OLE DB 공급자에 대 한 공급자 수준 0 표준을 충족 하도록 하려면 (ADO 적합성 테스트 포함) OLE DB 적합성 테스트를 실행 합니다. (수준 0의 설명에 대 한 테스트에 대 한"OLE DB 수준 0 규칙"에서 검색 [OLE DB Programmer's Guide](http://go.microsoft.com/fwlink/p/?linkid=121548)합니다. 이러한 테스트와 관련된 설명서는 Visual c + + Data Access SDK에 포함 됩니다. 이러한 테스트 다른 집계 하는 경우에 공급자 실행 되도록 도움이 [서비스 공급자](../../data/oledb/ole-db-resource-pooling-and-services.md) 속성을 추가 하거나 수정할 경우 특히 유용 합니다. 규칙 테스트에 대 한 자세한 내용은 Visual Studio Cd 중 하나에 있는 Data Access SDK에 대 한 추가 정보 파일을 참조 하세요.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿을 사용하여 작업](../../data/oledb/working-with-ole-db-provider-templates.md)