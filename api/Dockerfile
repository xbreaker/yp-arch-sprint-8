FROM eclipse-temurin:17-jdk-jammy

# Установка Maven
RUN apt-get update && apt-get install -y maven

WORKDIR /app

# Копируем только POM файл сначала для эффективного кэширования
COPY pom.xml .

# Скачиваем зависимости
RUN mvn dependency:go-offline

# Копируем исходный код
COPY src ./src

# Собираем приложение
RUN mvn clean package -DskipTests

EXPOSE 8081

CMD ["java", "-jar", "target/reports-app-*.jar"]