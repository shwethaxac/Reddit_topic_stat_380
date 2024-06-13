library(data.table)
library(caret)

# load in data 
test<-fread("~/Desktop/kaggle_test.csv")
train<-fread("~/Desktop/kaggle_train.csv")
test_emb<-fread("~/Desktop/test_emb.csv")
train_emb<-fread("~/Desktop/train_emb.csv")

# write in data 
fwrite(test,"~/Desktop/380_f/reddit/project/volume/data/raw/kaggle_test.csv")
fwrite(train,"~/Desktop/380_f/reddit/project/volume/data/raw/kaggle_train.csv")
fwrite(test_emb,"~/Desktop/380_f/reddit/project/volume/data/raw/test_emb.csv")
fwrite(test_train,"~/Desktop/380_f/reddit/project/volume/data/raw/train_emb.csv")

# change reddit col to numeric
train$reddit <- factor(train$reddit)
train$reddit <- as.numeric(train$reddit)

# add reddit col to test table
test$reddit <- 11

# make a master table
train$text <- NULL
test$text <- NULL
train$train <- 1
test$train <- 0

master_train <- cbind(train, train_emb)
master_test <- cbind(test, test_emb)
master <- rbind(master_train, master_test)

fwrite(master,"~/Desktop/reddit_master.csv")
fwrite(master_train,"~/Desktop/master_train.csv")
fwrite(master_test,"~/Desktop/master_test.csv")

# write out to interim 
fwrite(master,"~/Desktop/380_f/reddit/project/volume/data/interim/reddit_master.csv")
fwrite(master_train,"~/Desktop/380_f/reddit/project/volume/data/interim/reddit_master_train.csv")
fwrite(master_test,"~/Desktop/380_f/reddit/project/volume/data/interim/reddit_master_test.csv")
