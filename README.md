CREATE SCHEMA `onibus` DEFAULT CHARSET=utf8mb3 COLLATE=utf8_bin;

CREATE TABLE `onibus` (
  `id` int NOT NULL AUTO_INCREMENT,
  `placa` varchar(10) COLLATE utf8_bin NOT NULL,
  `quantidade_assento`INT NOT NULL,
  `ativo` tinyint DEFAULT '1',
  PRIMARY KEY (`id`),
  UNIQUE KEY `placa_UNIQUE` (`placa`)
) ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT CHARSET=utf8mb3 COLLATE=utf8_bin;


CREATE TABLE `assento` (
  `id` int NOT NULL AUTO_INCREMENT,
  `id_onibus` int NOT NULL,
  `numero` int NOT NULL,
  `ativo` tinyint DEFAULT '1',
  PRIMARY KEY (`id`),
  UNIQUE KEY `nome_UNIQUE` (`nome`)
) ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT CHARSET=utf8mb3 COLLATE=utf8_bin;


CREATE TABLE `viagem` (
  `id` int NOT NULL AUTO_INCREMENT,
  `id_onibus` int NOT NULL,
  `cidade_origem` varchar(100) COLLATE utf8_bin NOT NULL,
  `data_saida` varchar(10) COLLATE utf8_bin NOT NULL,
  `horario_saida` varchar(5) COLLATE utf8_bin NOT NULL,
  `cidade_destino` varchar(100) COLLATE utf8_bin NOT NULL,
  `data_chegada` varchar(10) COLLATE utf8_bin NOT NULL,
  `horario_previsto_chegada` varchar(5) COLLATE utf8_bin NOT NULL,
  `ativo` tinyint DEFAULT '1',
  PRIMARY KEY (`id`),
  KEY `fk_viagem_onibus_idx` (`id_onibus`),
  CONSTRAINT `fk_viagem_onibus` FOREIGN KEY (`id_onibus`) REFERENCES `onibus` (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT CHARSET=utf8mb3 COLLATE=utf8_bin;


CREATE TABLE `passageiro` (
  `id` int NOT NULL AUTO_INCREMENT,
  `nome` varchar(150) COLLATE utf8_bin NOT NULL,
  `sexo` varchar(1) COLLATE utf8_bin NOT NULL,
  `email` varchar(150) COLLATE utf8_bin NOT NULL,
  `cpf` varchar(14) COLLATE utf8_bin NOT NULL,
  `celular` varchar(14) COLLATE utf8_bin NOT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `email_UNIQUE` (`email`),
  UNIQUE KEY `cpf_UNIQUE` (`cpf`)
) ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT CHARSET=utf8mb3 COLLATE=utf8_bin;

INSERT INTO onibus (placa, quantidade_assento, ativo) VALUES ('ABC1234', 40, 1);
INSERT INTO onibus (placa, quantidade_assento, ativo) VALUES ('XYZ5678', 50, 1);
INSERT INTO onibus (placa, quantidade_assento, ativo) VALUES ('LMN9101', 45, 1);
INSERT INTO onibus (placa, quantidade_assento, ativo) VALUES ('PQR2345', 35, 1);
INSERT INTO onibus (placa, quantidade_assento, ativo) VALUES ('STU6789', 60, 1);
INSERT INTO onibus (placa, quantidade_assento, ativo) VALUES ('VWX3456', 55, 1);
INSERT INTO onibus (placa, quantidade_assento, ativo) VALUES ('YZA7890', 48, 1);
INSERT INTO onibus (placa, quantidade_assento, ativo) VALUES ('BCD1234', 50, 1);
INSERT INTO onibus (placa, quantidade_assento, ativo) VALUES ('EFG5678', 42, 1);
INSERT INTO onibus (placa, quantidade_assento, ativo) VALUES ('HIJ9101', 38, 1);
