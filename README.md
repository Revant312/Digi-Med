# Digi-Med
Medical App

import React from 'react';
import { SafeAreaView, View, FlatList, StyleSheet, Text, StatusBar, Image } from 'react-native';
	
const DATA = [
  {
    id: 'bd7acbea-c1b1-46c2-aed5-3ad53abb28ba',
    title: 'Digital MedRecord',
  },
];

const Item = ({ title }) => (
  <View style={styles.item}>
    <Text style={styles.title}>{title}</Text>
  </View>
);

const App = () => {
  const renderItem = ({ item }) => (
    <Item title={item.title} />
  );

  return (
    <SafeAreaView style={styles.container}>
      <FlatList
        data={DATA}
        renderItem={renderItem}
        keyExtractor={item => item.id}
      />
      <Image source={{
        width: 400,
        height: 400,
        uri: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS9enT11o9iDNvQN8pF2qbjCwYefBqsM68CMCCk9NO0Hxg_FUaquIv3zPmDZdOGBPJW-E4&usqp=CAU" }} 
      />
    </SafeAreaView>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: 'lightgreen',
    alignItems: 'center',
    justifyContent: 'center',
    marginTop: StatusBar.currentHeight || 0,
  },
  item: {
    backgroundColor: 'lightgreen',
    padding: 42,
    marginVertical: 14,
    marginHorizontal: 0,
  },
  title: {
    fontSize: 64,
  },
});

export default App;

