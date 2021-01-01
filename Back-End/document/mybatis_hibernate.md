# Mybatis VS Hibernate

## SQL Mapper
* SQL <- ���� -> Object �ʵ�
* SQL Mapper�� SQL �������� ���� �����ͺ��̽� �����͸� �ٷ��.
  * ��, SQL Mapper�� SQL�� �������� �Ѵ�.
  * EX) Mybatis, JdbcTemplates ��

<br>

## ORM(Object-Relational Mapping) , ��ü - ���� ����
* �����ͺ��̽� ������ <- ���� -> Object �ʵ�
  * ��ü�� ���� ���������� �����ͺ��̽� �����͸� �ٷ��.
* ��ü�� ������ �����ͺ��̽��� �����͸� �ڵ����� ����(����)���ִ� ���� ���Ѵ�.
  * ORM�� �̿��ϸ� SQL Query�� �ƴ� �������� �ڵ�(�޼���)�� �����͸� ������ �� �ִ�.
  * ��ü ���� ���踦 �������� SQL�� �ڵ����� �����Ѵ�.

## JPA(Java Persistent API)
![](2021-01-02-03-47-29.png)
java ORM ����� ���� API ǥ�� ����, Java���� �����ϴ� API

## Hibernate
* JPA�� ����ü �� �ϳ�
* Hibernate�� �����ϴ� �޼��� ���ο����� JDBC API�� �����Ѵ�.
* ��ü���������� ����Ѵ�

```
@Entity
public class User {
	@Id
	private String id;
	private String pwd;
	private String nickname;
 }
```

## Mybatis
* �����ڰ� ������ SQL, ���� ���ν��� �׸��� �� ���� ��� ������ �����ϴ� SQL Mapper�̴�.
* JDBC�� ó���ϴ� ��� �κ��� �ڵ�� �Ķ���ͼ��� �� ��� ������ ������ش�.
* JPA�� ���ؼ� ������ ������ ����� ������ ���δ�.

<br>

![](2021-01-02-03-48-27.png)

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE mapper
PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN"
"http://mybatis.org/dtd/mybatis-3-mapper.dtd">
<mapper namespace="com.naver.dbtest.repo.UserRepo">

	<insert id="insert" parameterType="user">
		insert into
		user(id,pwd,nickname) values(#{id},#{pwd},#{nickname})
	</insert>

	<select id="selectOne" parameterType="user" resultType="user">
		select
		id, pwd, nickname from user where id = #{id}
	</select>

	<select id="selectAll" resultType="user">
		select
		id, pwd, nickname from
		user
	</select>
</mapper>
```
