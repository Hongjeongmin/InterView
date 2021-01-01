# �����ͺ��̽� Isolation Level (������)

## �����ͺ��̽��� �б� �̻� ���� (Read Phenomena)
<br>

|����|����|�ذ���|
|------|-----|---------|
|Dirty Read|Ʈ����� T1 ���� A = 5 �� Update �ϰ� ���� commit �� �ʾҴµ� �ٸ� Ʈ�����  T2�� �� A ���� ���� �� �ֵ��� ����ϴ� ��� Dirty Read�� �߻� �Ҽ� �ִ�. ��.   T1�� Update�� ������ �� ���� commit �� ���ߴµ� �ٸ� Ʈ����� T2�� A �� select ���� �� 5 �� ���� ��� , T1 Ʈ������� rollback�� ���� ��� �ᱹ A ���� 5�� �ƴԿ��� T2 �� 5�� �߸� �д� (Dirty Read) ������ �߻��Ѵ�|���� Lock �� �ɾ T1�� A �� �����ϰ� �ִ� ���� �ٸ� Ʈ������� �������� ���ϰ� ��.|
|Non Repeatable Read|T1 Ʈ������� ���� ������ �ι� �����ߴµ� �� ������� �ٸ� ���, �� T1 ��  select �� �ι� �ϴ� ���̿� T2 Ʈ������� update �� delete �� �� ���|Ʈ����� �Ϸ� �ñ��� ����/���� ����|
|Phantom Read|T1 Ʈ������� ���� ������ �ι� ���� �� ù��° ����ÿ� ���� ���ڵ尡 �ι�° ����ÿ� Ƣ�� ������ ��� |T1 Ʈ������� ���� �����ʹ� T2 Ʈ����ǿ��� ����, �������� ���� �� �ƴ϶� �߰��� ���ο� ���ڵ� ����(Insert)���� ����|

Dirty Read -> Non Repeatable Read -> Phantom Read �� ���� �ϱ�, ��������, ���� ������ �޶�����.

## �����ͺ��̽��� Isolation Level (������) ����
<br>

|����|����|�б� �̻� ����|
|------|---|---|
|Read Uncommitted |Ʈ�����  T1�� ���� commit ���� ���� �����͸� �ٸ� Ʈ����� T2�� Read �ϴ� ���� ���|Dirty Read <br> ����Ŭ�� ������|
|Read Committed|Ʈ�����  T1�� commit �� �� �����͸� �ٸ� Ʈ����� T2�� Read �ϴ� ���� ���|Dirty Read�� ���� �� ������ Non Repeatable Read�� Phantom Read �� ���� ������ (��κ��� DBMS�� ä��)|
|Repeatable Read|���� Ʈ����� T1�� ���� �����ʹ� T1�� ����� �� ������ �ٸ� Ʈ������� ����/���� (Update/Delete) �� ������� ���� �� ����(Insert) �� ��� ��.|Dirty Read�� Non Repeatable Read������ �߻��� ������ ������ Phantom Read �� ���� ������|
|Serializable|	���� Ʈ����� T1�� ���� �����ʹ� T�� ����� �� ���� �ٸ� Ʈ������� ����/������ ���� ���� ���� ������� ����|Dirty Read�� Non Repeatable Read�� Phantom Read ���� ��� ���� �� ���� (�Ϻ������� ���� ���������δ� �Ұ��ɿ� ������)|

<br>

## Isolation Level �� �б� �̻� ������ ����
<br>

|Isolation Level|Dirty Read|Non Repeatable Read|Phantom Read|
|------|---|---|---|
|Read Uncommitted |����|����|����|
|Read Committed|�Ұ���|����|����|
|Repeatable Read|�Ұ���|�Ұ���|����|
|Serializable|�Ұ���|�Ұ���|�Ұ���|