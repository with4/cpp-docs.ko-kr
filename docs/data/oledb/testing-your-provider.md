---
title: "공급자 테스트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- OLE DB providers, testing
ms.assetid: bf824fe4-81af-4ffb-beb3-4fa2928dc450
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 551ccfdf236eb5828b1d41ae8867acdb259b1d4f
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2018
---
# <a name="testing-your-provider"></a>공급자 테스트
공급자를 해제 하기 전에 다음 테스트를 아래 순서로 수행 해야 합니다. 이러한 테스트의 대부분 사용자가 제대로 공급자 작동 하는지 확인 합니다.  
  
1.  사용 하 여 공급자를 테스트 한 [소비자](../../data/oledb/creating-an-ole-db-consumer.md) OLE DB 소비자 템플릿 작성 된 응용 프로그램입니다. 테스트 소비자는 공급자 (추가 또는 수정 하는 모든 코드)의 모든 기능 영역을 포함 해야 합니다.  
  
2.  ADO로 작성 하는 소비자 응용 프로그램을 사용 하 여 공급자를 테스트 합니다. 대부분의 개발자 (특히: Microsoft Visual Basic 및 C# 개발자) 소비자 응용 프로그램에 대 한 ADO 또는 ADO.NET을 사용 합니다. 테스트 소비자는 공급자의 모든 기능 영역을 포함 해야 합니다. ADO 소비자 응용 프로그램의 예제를 보려면 [ADO 코드 예제에서는 Microsoft Visual Basic](https://msdn.microsoft.com/en-us/library/ms807514.aspx)합니다.  
  
3.  OLE DB 공급자에 대 한 공급자 수준 0 표준을 충족 하는지 확인 하는 OLE DB 적합성 테스트 (ADO 적합성 테스트 포함)를 실행 합니다. (에 대 한 설명은 수준 0, "OLE DB 수준 0 적합성 테스트"에 검색할 [OLE DB Programmer's Guide](http://go.microsoft.com/fwlink/p/?linkid=121548)합니다. 이러한 테스트 및 관련된 설명서에는 Visual c + + Data Access SDK에 포함 되어 있습니다. 이러한 테스트는 또한 다른 집계 하는 경우에 공급자에 실행 되는지 확인 하는 데 도움이 [서비스 공급자](../../data/oledb/ole-db-resource-pooling-and-services.md) 있으며이 수정 하거나 속성을 추가 하는 경우 특히 유용 합니다. 규칙 테스트에 대 한 자세한 내용은 Visual Studio Cd 중 하나에 있는 Data Access SDK에 대 한 추가 정보 파일을 참조 하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿을 사용하여 작업](../../data/oledb/working-with-ole-db-provider-templates.md)